---
id: "GAME-014"
nome: "Universo Único, Menu de Entrada e Modos de Sessão"
status: "PLANEJADO"
funcao: "Arquitetura de entrada, campanha individual, solo, grupo privado e mundo público"
relacionados:
  - "GAME-001"
  - "GAME-009"
  - "GAME-011"
  - "GAME-012"
  - "GAME-013"
  - "GAME-015"
atualizado_por: "ChatGPT"
data_atualizacao: "2026-10-13"
---

# Universo Único, Menu de Entrada e Modos de Sessão

> **DECISÃO DE DESIGN APROVADA EM 13/10/2026. IMPLEMENTAÇÃO PENDENTE.** Este documento define o comportamento desejado. Não declara que menu, teleporte, sessões privadas, convites ou bloqueios estejam funcionais no Studio.

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
Sequência **pretendida**, sujeita a auditoria da inicialização real:
1. Carregamento técnico mínimo necessário do Roblox e apresentação da abertura cinematográfica já existente (30 s). Não prometer menu antes de qualquer carregamento.
2. Ao terminar a abertura, apresentar **menu principal** com fundo derivado do último enquadramento, sem título/logotipo gravado na imagem; logo e botões são elementos próprios da UI.
3. Botões: **Continuar História / Jogar Solo** (disponível); **Jogar com Amigos** e **Mundo Público** (visíveis, atenuados, não acionáveis até desbloqueio); **Configurações**, **Conquistas** e **Créditos** (itens graduais, conforme implementação).
4. Ao escolher Solo, carregar/iniciar a sessão narrativa e então a **cutscene de John na escrivaninha** (25 s) quando for a primeira vez, preservando a sequência existente, leitura/coleta do diário e a missão **A Primeira Lâmina**. Ao retornar com introdução concluída, não forçar repetição; comportamento de reprises será decidido.
5. Quando a Insígnia estiver registrada no perfil, permitir escolher sessão por convite ou pública. Verificações no servidor são obrigatórias: bloquear somente na interface não basta.

Abertura cinematográfica e cutscene na casa são coisas distintas. Não refazer seus conteúdos ou quebrar as transições. Preparar UI responsiva em desktop, celular e controle, aproveitando sistemas existentes. Configurações futuras: volume geral, música, efeitos, controles, sensibilidade de câmera e elementos da HUD. **Escopo inicial do menu: fluxo e fundamentos visuais; não implantar todas as opções de uma vez.**

## 4. Progressão multiplayer e cooperação
- Missões, requisitos, diálogos e recompensas são avaliados individualmente pelo servidor para cada jogador.
- Companheiros podem acompanhar explorações, lutas e atividades e aceitar missões compatíveis; ajudar não concede automaticamente a etapa narrativa pendente.
- Recompensas e elegibilidade de loot permanecem individuais, respeitando os sistemas existentes GAME-011/012/013 e suas regras específicas.
- Salvamento/transferência entre servidores não deve duplicar itens ou sobrescrever dados. Planejar controle de concorrência de sessões, gravação segura, recuperação de falha e validação no servidor.
- Ponto de entrada/retorno deve considerar o progresso individual e a natureza da sessão, sem alterar a história de outros participantes.
- Convites de grupo são controlados pelo líder. Comportamento após saída/desconexão do líder, reconexão, limite de convidados e política de remoção ainda estão **PENDENTES**.

## 5. Arquitetura técnica a avaliar, não implementação aprovada
O Roblox oferece recursos para múltiplos *places* na mesma experiência, teleportes, servidores reservados e dados persistentes; a topologia final (um place com roteamento ou places especializados) exige inspeção dos places e scripts atuais e teste real. O menu poderá residir em um lobby/place inicial técnico; isso **não está decidido**. Não migrar automaticamente Place1 nem Mundo Livre, não substituir Place2 e não criar novos places sem estudo e autorização. Teleporte e servidores reservados devem ser testados em ambiente publicado de teste, já que testes locais do Studio não cobrem tudo.

Preferir **um perfil e serviços centrais**, com regras de sessão por contexto, em vez de inventários, moedas e catálogos duplicados. Validar chamadas remotas, permissões e replicação para múltiplos jogadores.

## 6. Dependência de desbloqueio
Ambos **Jogar com Amigos** e **Mundo Público** são liberados por uma condição persistente única: conclusão da formação inicial na guilda e recebimento da **Insígnia da Guilda**, registrada na **Carteira da Guilda**. Detalhes da formação, classes e conquistas: GAME-015.

Até essa liberação, apenas a campanha Solo é acionável, inclusive diante de convites ou tentativas de teleporte direto. Revalidar elegibilidade no servidor.

## 7. Pendências deliberadas
- Limites de participantes do privado e público.
- Fluxo de convite, expiração, saída do líder, continuidade da sessão e reconexão.
- Quais trechos da missão principal poderão ocorrer no público sem colisão narrativa.
- Persistência e restauração de cenas, checkpoints e locais de entrada.
- Interface e opções efetivas de configurações, imagens finais, créditos e eventuais reprises.
- Topologia definitiva dos places e impacto nas rotinas de carregamento existentes.
- Política de progressão cooperativa para atividades futuras e recompensas compartilháveis.

## 8. Fases de implementação, sem publicação automática
1. **Auditar** carregamento atual, abertura, cutscene, dados persistentes, places, HUD e fluxo de gameplay; desenhar transição para o menu sem quebrar a intro.
2. **Menu visual e estados:** tela pós-abertura, botões bloqueados com requisito explícito, Solo funcional sem regressão, Configurações e Conquistas com escopo definido.
3. **Fundação de perfil e desbloqueios:** registro persistente, verificação servidor e testes de dois jogadores.
4. **Sessões/convites/teleporte:** modo solo reservado, grupo com anfitrião e público, testes externos de transferência e concorrência.
5. **Expansões posteriores:** guilda jogável, treinamento, classes, missões cooperativas e opções ampliadas. O desbloqueio real depende da formação estar funcional; não antecipar concessões.

**Estado:** decisão arquitetural documentada; Studio não verificado para esta funcionalidade, nada deste documento deve ser marcado como implementado.
