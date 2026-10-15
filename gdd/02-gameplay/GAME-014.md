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
data_atualizacao: "2026-10-15"
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
