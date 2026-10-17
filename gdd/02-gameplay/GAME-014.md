---
id: "GAME-014"
nome: "Universo Único, Menu de Entrada e Modos de Sessão"
status: "EM_DESENVOLVIMENTO"
funcao: "Arquitetura de entrada, campanha individual, solo, grupo privado e mundo público"
relacionados:
  - "GAME-001"
  - "GAME-009"
  - "GAME-011"
  - "GAME-012"
  - "GAME-013"
  - "GAME-015"
atualizado_por: "Codex"
data_atualizacao: "2026-10-16"
---

# Universo Único, Menu de Entrada e Modos de Sessão

> **Estado conferido em 15/10/2026:** menu visual e integração Solo implementados/testados localmente. Sessões privadas, Mundo Público, formação/insígnia, isolamento multiplayer e teletransportes permanecem planejados. Este documento distingue a execução atual das regras futuras.

## 1. Princípio central
**Batalhas Poderosas tem um universo narrativo único e um perfil persistente por jogador.** Solo, grupo privado e servidor público são maneiras de acessar o mesmo jogo, não três campanhas, personagens, economias ou inventários separados. Ao trocar de sessão o jogador preserva: identidade/protagonismo da própria campanha, progresso de missões e objetivos, diário, moedas, inventário/alforge, equipamentos, habilidades, pontos de habilidade, classes aprendidas, inscrição/insígnia da guilda e conquistas.

Cada jogador é protagonista de sua própria jornada de John. Nenhum anfitrião assume o controle da história de outro personagem; um jogador adiantado não conclui automaticamente as etapas de quem acabou de entrar. O nível de progressão do anfitrião não é copiado aos convidados.

## 2. Três formas de sessão
| Modo | Acesso | Propósito | Progresso |
|---|---|---|---|
| Campanha Solo | Disponível desde o primeiro acesso | Abertura pessoal, introdução na casa de John, missão principal e exploração no ritmo próprio | Individual, compartilhado entre modos |
| Jogar com Amigos | Desbloqueado pela Insígnia da Guilda | Sessão reservada por convite, com líder/anfitrião que controla convites; campanha individual e atividades cooperativas | Cada participante mantém o próprio |
| Mundo Público | Desbloqueado pela Insígnia da Guilda | Vila compartilhada, atividades sociais, exploração, fazenda, coleta, economia, itens raros, missões secundárias e atividades compatíveis | Cada participante mantém o próprio |

**Grupo de aventura** é uma reunião de jogadores sob liderança de anfitrião; não é uma guilda concorrente. A vila tem uma única instituição de guilda para os aventureiros (ver GAME-015). Os convidados não ganham os direitos de emitir convites no modelo inicial.

### Limites de atividades por contexto
Cenas narrativas que exigem um ambiente exclusivo, especialmente John na única casa da vila, são pessoais e não devem deslocar/interromper outros jogadores de um servidor público. No solo, executar normalmente. Em grupo privado, uma apresentação pessoal não deve controlar câmera ou personagens dos colegas; pode usar instância/ambiente isolado ou outro mecanismo validado. No público, priorizar atividades do mundo compartilhado e impedir a execução conflitante de cenas exclusivas; um novato sem introdução concluída inicia pela experiência solo.

O mundo público não é outra lore nem um apagamento das missões principais. **Quais objetivos principais poderão avançar no público, e quais exigirão ambiente pessoal, serão catalogados por missão**, sem afirmar agora que toda campanha funciona ali. Evitar duplicar fisicamente a Casa de John para cada participante.

## 3. Menu principal e abertura existente

Ordem implementada: **entrada → Menu Principal → seleção Solo → preparação + intro recorrente → cutscene pessoal se pendente → gameplay**.

- Solo disponível; Amigos e Mundo Público visíveis com bloqueio e requisito da Insígnia. Sua presença não representa sessões multiplayer funcionais.
- A intro atual é exibida também para quem retorna. `CampanhaConfig` centraliza o catálogo, hoje somente `ArkanAtual` / `BP_AberturaConfig`, e a política futura de evitar repetição consecutiva. Não há outras intros ativas.
- O servidor decide a elegibilidade da cutscene. O perfil existente foi reconciliado para versão 5 com `Narrativa.IntroducaoJohnConcluida` e `Narrativa.UltimaIntroId`. Saves antigos sem marcador recebem a cena uma vez; não se deduz sua conclusão pela espada ou pelo Piso 1.
- Conclusão pessoal é confirmada depois da sequência e do posicionamento seguro sob o fade, com tempo mínimo, commit persistente e idempotência. Interrupção anterior mantém a cena pendente. Falha de confirmação não libera a entrada desprotegida.
- Retorno seguro: `CasaJohnFrenteEscrivaninha`, com checagem de piso e espaço livre. Não há salvamento geral da última coordenada. Inventário, moedas, diário e missões continuam no mesmo perfil; cada sessão começa sem itens equipados, preservando a posse.
- A liberação exige assets essenciais no cliente, perfil, Fase1Pronta e confirmação do servidor. Se a intro acabar antes, manter a transição protegida até prontidão real.
- Intro e cutscene existentes foram preservadas. O áudio da cutscene segue até o fim antes da música ambiente. O menu usa o tema da vila (`106121868942949`) em loop e volume moderado, coordenado por contexto para não sobrepor a intro.
- Interface responsiva com logo oficial separado, PNGs reutilizáveis, estados normal/destaque/pressionado/bloqueado e área segura. Refinamento de 14/10 usa 22 recursos visuais; os 21 PNGs originais foram preservados como referência. Configurações, Conquistas e Créditos têm navegação conforme a implementação; a existência de uma tela não certifica todas as opções futuras.

### Componentes atuais

`ReplicatedFirst.BP_MenuPrincipal`, `CarregamentoInicial`, `ReplicatedStorage.BP_MenuPrincipal.CampanhaConfig`, `ServerScriptService.SistemasGameplay.MenuPrincipalService`, `GerenciadorAberturaFase1` e os controladores existentes de cutscene/persistência. Não foi criado perfil paralelo.

### Medições e testes registrados

| Marco local | Antes | Depois da Etapa 2 |
|---|---:|---:|
| Fase1Pronta observada | 1,43 s | 0,70 s |
| Perfil disponível | 2,25 s | 2,44 s |
| Recursos do menu | 3,05 s | 3,31 s |
| Solo até gameplay no retorno | 62,95 s | 35,51 s |

Amostras únicas de Studio, com cache/condições diferentes; não demonstram ganho geral de carregamento. A diferença da última linha decorre principalmente de não repetir a cutscene pessoal. A espera induzida de 128,51 s testou mundo lento, não desempenho normal.

Play cobriu perfil novo em memória, retorno com marcador concluído, câmera/controles liberados e entrada protegida além da duração da intro. Testes de serviço cobriram conclusão antecipada recusada, idempotência, reabertura em memória e preservação de inventário/moedas/missões/diário. Refinamento visual teve testes em simuladores mobile e desktop. Não houve nesta etapa desconexão física, teste multiplayer, teleporte, telefone ou controle físicos. Não declarar VALIDADO com base nesses ensaios.

## 4. Progressão multiplayer e cooperação
- Missões, requisitos, diálogos e recompensas são avaliados individualmente pelo servidor para cada jogador.
- Companheiros podem acompanhar explorações, lutas e atividades e aceitar missões compatíveis; ajudar não concede automaticamente a etapa narrativa pendente.
- Respeitar as regras específicas existentes: corpos comuns e Baú Falso têm saque compartilhado (GAME-011); Baú Verdadeiro e Guardião têm direitos individuais (GAME-013). Não converter todo loot para um único regime.
- Salvamento/transferência entre servidores não deve duplicar itens ou sobrescrever dados. Planejar controle de concorrência de sessões, gravação segura, recuperação de falha e validação no servidor.
- Ponto de entrada/retorno deve considerar o progresso individual e a natureza da sessão, sem alterar a história de outros participantes.
- Convites de grupo são controlados pelo líder. Comportamento após saída/desconexão do líder, reconexão, limite de convidados e política de remoção ainda estão **PENDENTES**.

## 5. Arquitetura atual e separação futura
O Roblox oferece recursos para múltiplos *places* na mesma experiência, teleportes, servidores reservados e dados persistentes; a topologia final (um place com roteamento ou places especializados) exige inspeção dos places e scripts atuais e teste real. O menu poderá residir em um lobby/place inicial técnico; isso **não está decidido**. Não migrar automaticamente Place1 nem Mundo Livre, não substituir Place2 e não criar novos places sem estudo e autorização. Teleporte e servidores reservados devem ser testados em ambiente publicado de teste, já que testes locais do Studio não cobrem tudo.

Preferir **um perfil e serviços centrais**, com regras de sessão por contexto, em vez de inventários, moedas e catálogos duplicados. Validar chamadas remotas, permissões e replicação para múltiplos jogadores.

## 6. Dependência de desbloqueio
Ambos **Jogar com Amigos** e **Mundo Público** são liberados por uma condição persistente única: conclusão da formação inicial na guilda e recebimento da **Insígnia da Guilda**, registrada na **Carteira da Guilda**. Detalhes da formação, classes e conquistas: GAME-015.

Até essa liberação, apenas a campanha Solo é acionável, inclusive diante de convites ou tentativas de teleporte direto. Revalidar elegibilidade no servidor.

## 7. Pendências deliberadas

- Sessões privadas/públicas, convites, saída do líder, limites e reconexão reais.
- Registro da Insígnia, formação e desbloqueios (GAME-015).
- Isolamento das cenas pessoais, checkpoint fora da casa e salvamento de posição por contexto.
- Topologia de Places e testes externos de transferência/concorrência.
- Conteúdo adicional de configurações/conquistas, alternativas de intro e homologação em dispositivos físicos.

## 8. Próximas fases

Menu e continuidade Solo já possuem implementação. As fases seguintes devem auditar a separação de sessões e a elegibilidade, preservando o perfil e os serviços centrais. Não habilitar multiplayer somente removendo o cadeado visual; não criar outros Places ou conceder insígnia automaticamente. Publicação do jogo exige autorização própria.

## Limitação técnica atual e exceção administrativa planejada

O Place ainda prepara mapa, NPCs e serviços antes da seleção Solo. Não foi feita migração, sessão reservada ou teleporte. A cutscene ainda atua sobre porta/cadeira no ambiente do servidor: sua execução com convidados exige isolamento antes de habilitar os modos.

O usuário solicitou uma exceção administrativa futura para convidar testadores pelos meios padrão da Roblox, mesmo sem a formação inicial. Essa política precisa de autorização validada no servidor e não deve copiar progresso nem interromper a cutscene do convidado. **Não está certificada como implementada**; identidade administrativa, escopo e testes devem ser conferidos na etapa multiplayer.

## 9. Acompanhamento das etapas do Menu Principal — 16/10/2026

> **Registro de planejamento e evidências relatadas, não homologação.** Os resultados das Etapas 3 e 4 abaixo provêm dos relatórios de execução do Studio de 15 e 16/10/2026, ainda sem revisão direta do responsável, publicação ou migração dos perfis de produção. A descrição histórica de perfil único e seleção Solo nas seções anteriores corresponde à arquitetura anterior à Etapa 3; a arquitetura local mais recente usa **uma conta com até três jornadas independentes**, mais Partida Livre temporária. A adoção em produção está bloqueada até implantação coordenada.

### Estados de acompanhamento

- **PROGRAMADO:** aprovado para execução futura, ainda não implementado.
- **EM ANDAMENTO:** implementação em execução.
- **IMPLEMENTADO / TESTADO LOCALMENTE:** agente relatou execução e testes controlados, sem homologação do responsável.
- **AGUARDANDO VALIDAÇÃO:** depende de inspeção e aceite do responsável; não equivale a VALIDADO.
- **VALIDADO:** somente após confirmação expressa do responsável e evidências apropriadas.
- **BLOQUEADO:** há dependência técnica ou autorização pendente.
- **ADIADO:** melhoria futura fora da prioridade atual, sem cancelamento.

### Quadro de etapas

| ID | Etapa | Estado | Próxima ação / ressalva |
|---|---|---|---|
| MENU-01 | Interface visual, recursos e estrutura inicial | IMPLEMENTADO / TESTADO LOCALMENTE; AGUARDANDO VALIDAÇÃO | Confirmar visual e funcionamento em dispositivos reais. |
| MENU-02 | Introdução, cutscene de John e retomada | IMPLEMENTADO / TESTADO LOCALMENTE; AGUARDANDO VALIDAÇÃO | Confirmar regressões e continuidade após as etapas posteriores. |
| MENU-03 | Três espaços de campanha e Partida Livre | IMPLEMENTADO / TESTADO LOCALMENTE; AGUARDANDO VALIDAÇÃO | Revisar migração, isolamento, dados legados e implantação coordenada. |
| MENU-04 | Configurações e acessibilidade | IMPLEMENTADO / TESTADO LOCALMENTE; AGUARDANDO VALIDAÇÃO | Validar controles, persistência global e dispositivos físicos. |
| MENU-05 | Perfil e Conquistas | PROGRAMADO | Auditar dados reais por conta e por jornada; não inventar conquistas nem recompensas. |
| MENU-06 | Jogar com Amigos | PROGRAMADO | Projetar e testar exceção para amigos autorizados em desenvolvimento; preservar proteção das cenas e dos dados individuais. |
| MENU-07 | Validação final do Menu Principal | PROGRAMADO | Regressão integral, testes físicos, persistência, retorno e aceite antes da liberação. |

### Checklist de implementação e homologação

- [x] **MENU-01:** implementação visual inicial relatada.
- [x] **MENU-02:** entrada Solo e cinemáticas implementadas e testadas localmente segundo relatório.
- [x] **MENU-03:** três jornadas, seleção, exclusão protegida e Partida Livre implementadas em edição local, com testes isolados relatados.
- [x] **MENU-04:** preferências globais de áudio, câmera compatível, legibilidade e interface implementadas em edição local, com testes controlados relatados.
- [ ] Validar pessoalmente as Etapas 1–4 e conferir o salvamento integral da edição do Studio.
- [ ] Planejar e executar a **migração de produção** dos saves legados sem coexistência incompatível de servidores antigos; atualmente desabilitada.
- [ ] Implementar **MENU-05: Perfil e Conquistas** com estatísticas e marcos reais, separados por conta e jornada.
- [ ] Implementar **MENU-06: Jogar com Amigos**, inclusive autorização controlada de amigos testadores sem exigir insígnia durante o desenvolvimento; Mundo Público continua bloqueado.
- [ ] Executar **MENU-07: validação final**, inclusive aparelhos físicos, controle real, múltiplos clientes e recuperação após falhas.
- [ ] Registrar o aceite expresso do responsável antes de alterar o estado de qualquer etapa para VALIDADO.

### Melhorias futuras e pendências não bloqueantes da Etapa 4

| ID | Tema | Estado | Observação |
|---|---|---|---|
| MENU-F01 | Pré-carregamento inteligente durante o menu | ADIADO | Não é prioridade; medir benefício antes de implementar. |
| MENU-F02 | Remapeamento de comandos | PROGRAMADO | Requer integração específica com os controladores. |
| MENU-F03 | Sensibilidade de toque e controle | PROGRAMADO | Não certificada na Etapa 4. |
| MENU-F04 | Inversão vertical da câmera | PROGRAMADO | Exige análise dos controladores existentes. |
| MENU-F05 | Separar música e voz nos áudios mesclados | PROGRAMADO | Depende de assets de áudio separados. |
| MENU-F06 | Alternativas de introdução cinematográfica | PROGRAMADO | Respeitar catálogo e política de não repetição quando houver mais de uma. |
| MENU-F07 | Checkpoints adicionais e retomada contextual | PROGRAMADO | Não substituir o retorno seguro atual por coordenadas arbitrárias. |
| MENU-F08 | Homologação em celular, tablet e controle físicos | PROGRAMADO | Testes de layout/simulador não substituem dispositivo físico. |
| MENU-F09 | Diagnóstico de animações com falha de carregamento | PROGRAMADO | Investigar IDs 128184686642891, 96036565188344 e 76316048879551 sem atribuir a falha ao menu. |
| MENU-F10 | Aviso UIBlox/FoundationProvider | PROGRAMADO | Investigar apenas se houver impacto reproduzível; origem aparente em CorePackages do Roblox. |

### Dependências e regras de manutenção

1. **MENU-03 e MENU-04 não estão em produção.** A migração definitiva permanece desabilitada e a publicação depende de autorização separada.
2. **Jogar com Amigos** não deve ser dado como implementado por existir um botão. A exceção de desenvolvimento para amigos autorizados está pendente; não liberar Mundo Público nem contornar validações de servidor.
3. O registro de **conclusão de implementação** não equivale a validação humana ou homologação de produção.
4. Atualizar esta seção e as fichas relacionadas após cada relatório verificado, preservando IDs estáveis, histórico e dependências. Não inventar estados de sistemas não auditados.
5. Este checklist é documental. Uma futura visualização agregada no dashboard deverá ler dados estruturados do repositório, sem duplicar estados em código estático nem alterar o renderizador sem necessidade.

## 10. Decisão de design: progresso por jornada e conquistas globais — 16/10/2026

**APROVADO PARA DESIGN; implementação de conquistas ainda pendente.** Esta decisão prevalece sobre menções históricas a um perfil único ou a conquistas vinculadas a slots nas seções anteriores.

- **Conta Roblox:** identidade do jogador, preferências globais e coleção permanente de conquistas únicas, com registro de obtenção. O menu principal apresenta essas conquistas mesmo sem jornada selecionada.
- **Cada uma das três jornadas:** progresso narrativo, missões e objetivos (incluindo *A Primeira Lâmina*), inventário, moedas, equipamentos e demais estados da campanha, isolados dos outros slots.
- **Repetição em outra jornada:** refazer um marco não duplica a conquista global, nem a conquista já obtida conclui a missão, entrega itens ou transfere progresso para o novo slot.
- **Partida Livre:** continua temporária; a elegibilidade para conceder cada conquista global deve ser definida explicitamente. Na ausência de regra, não conceder.
- **Títulos de reconhecimento:** conceito futuro derivável de conquistas globais, sem nomes, quantidades, recompensas ou desbloqueios aprovados. Não confundir com Insígnia da Guilda.

**Execução em quatro entregas controladas:** MENU-05.1 Perfil global (identidade/avatar); MENU-05.2 resumo de progresso por jornada; MENU-05.3 catálogo, concessão e persistência de conquistas globais; MENU-05.4 integração e validação. Não considerar essas entregas implementadas apenas por estarem planejadas. Reutilizar os serviços existentes, preservar dados legados e não habilitar migração ou publicação sem autorização.
