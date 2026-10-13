---
id: "GAME-001"
nome: "Loop Principal e Progressão de Gameplay"
status: "CANONICO"
relacionados:
  - "ITEM-007"
  - "LORE-002"
  - "NPC-001"
  - "NPC-002"
  - "NPC-014"
  - "ITEM-001"
  - "ITEM-002"
  - "ITEM-003"
  - "DOS-004"
  - "BP-2026-002"
  - "GAME-014"
  - "GAME-015"
atualizado_por: "codex"
data_atualizacao: "2026-10-13"
---

# Loop Principal e Progressão de Gameplay

## 1. Loop Central
O ciclo de jogo equilibra:
1. Exploração & Coleta.
2. Artesanato & Preparação.
3. Combate & Missões.

## 2. Fase 1: preparação de John

### Fluxo narrativo/gameplay aprovado para desenvolvimento — 12/10/2026
1. Na primeira missão **A Primeira Lâmina**, John procura Mestre Cedric para obter uma espada de treinamento.
2. Cedric explica que precisa de **uma Madeira Ungida** e **um galho da Árvore Sagrada (Madeira Sagrada)**. Ele orienta John a procurar o padre na igreja, mas **não revela onde obter a Madeira Sagrada**.
3. O padre revela que, atrás da igreja, existe a **Árvore Ancestral**, árvore muito antiga de origem desconhecida, possivelmente vinda de um reino distante segundo a tradição oral. Sua forma e suas folhas são inteiramente quadradas, diferentes de todas as árvores conhecidas, inclusive da Árvore Sagrada.
4. Aos pés da Árvore Ancestral há um pedaço de madeira bruta, quadrada, que John recolhe. Para diferenciar origem e transformação, o item bruto pode ser apresentado como **Madeira da Árvore Ancestral**; sua nomenclatura definitiva no inventário ainda será validada.
5. John retorna ao padre, que unge o material. O item resultante é **Madeira Ungida**.
6. John pergunta ao padre onde obter o galho da Árvore Sagrada. O padre o encaminha ao **Ancião Eldrin**, no santuário da Árvore Sagrada.
7. John obtém a **Madeira Sagrada** com Eldrin e retorna a Cedric.
8. Cedric confere e consome **1 Madeira Ungida + 1 Madeira Sagrada**, fabrica a primeira espada de treinamento e entrega **um Escudo de Madeira (ITEM-007)** como cortesia única.
9. A missão é concluída individualmente e de forma persistente. O diálogo introdutório de Cedric deixa de ser oferecido a esse jogador, inclusive em sessões futuras. Cedric passa a oferecer seus serviços habituais, como manutenção e melhorias, à medida que forem implementados.

### Estado de implementação e pendências
- **Definição narrativa aprovada; implementação integral pendente.** Não confundir este fluxo com sistemas já funcionais no Studio.
- A Árvore Ancestral é um novo elemento/local de interesse **atrás da igreja**; requer ficha própria no catálogo de locais e implementação física, com tronco/madeira coletável aos pés.
- O padre ainda não tem nome nem ficha final; sua criação, diálogos e rito de unção estão pendentes.
- Rever fichas de itens, receita da espada, diálogos e objetivos sequenciais da missão, aproveitando inventário, notificações e navegação já existentes.
- Dividir a implementação em etapas médias e validar o ciclo completo antes de publicar.
- **Legado:** a Madeira Comum na Casa de John e a obtenção em estabelecimento comercial são fluxos antigos, não a nova rota narrativa. A expressão “Madeira Comum” pode descrever matéria-prima bruta, mas **não é o item final exigido por Cedric**.

### Escudo integrado ao circuito atual — 06/10/2026

A primeira forja existente com Cedric entrega a espada e **um Escudo de Madeira de cortesia**. O diálogo explicita a cortesia; a explicação pode ser consultada novamente sem repetir a recompensa. A receita e os materiais atuais da espada foram preservados.

O escudo entra no inventário persistente e pode ser equipado na mão secundária, mantendo a espada na mão direita. John levanta a guarda, caminha com velocidade reduzida e bloqueia ataques comuns pela frente; ao soltar, retoma ataque e dash. Ver **ITEM-007**, **GAME-002** e **GAME-003**.

Essa adição já funciona no circuito implementado. A nova rota da Árvore Ancestral, a unção pelo padre e a obtenção da Madeira Ungida permanecem pendentes de implementação; a entrega anterior não as implementou.


## 3. Princípio do arco
As etapas adicionais não existem apenas para alongar o tutorial. Cada deslocamento deve apresentar uma parte da vila, fortalecer relações com seus moradores e dar significado à fabricação da primeira espada deste ciclo.

Madeira Ungida e Madeira Sagrada são materiais distintos:
- Madeira Ungida: madeira comum obtida por John e depois ungida pelo padre.
- Madeira Sagrada: galho proveniente da Árvore Sagrada e ligado a Eldrin.

## 4. Inicialização e Liberação do Jogador
A abertura técnica permanece preparada para impedir que o jogador veja o mundo sendo montado antes de estar pronto.

Fluxo atual:
1. A tela inicial é exibida primeiro.
2. A rotina duplicada de abertura foi removida.
3. A Casa de John é preparada em paralelo com a inicialização geral do mundo.
4. John só é liberado quando está corretamente posicionado, a casa foi recebida pelo cliente e os recursos visuais essenciais foram carregados.
5. A tela de carregamento permanece cobrindo a abertura até a confirmação final do cliente.

### Medição local de referência — 20/09/2026
| Marco | Tempo aproximado |
| :--- | ---: |
| Carregamento base do jogo | 0,36 s |
| Posicionamento de John + chegada da casa | 5,40 s |
| Recursos visuais essenciais da casa prontos | 6,37 s |

> Valores de teste local, não metas canônicas de desempenho.

## 5. Estado Atual do Áudio
- IDs inválidos de sons locais que geravam avisos no console foram removidos.
- A música global da vila permanece em SoundService.
- O ID atual dessa música ainda apresenta falha de download e deve ser substituído futuramente.

## 6. Universo único, formação na guilda e modos de sessão — aprovado em 13/10/2026

**Decisão de design aprovada, implementação pendente:** o jogo preservará uma campanha e um perfil persistente por jogador em três tipos de entrada: Solo desde o começo; grupo privado com convites controlados pelo líder; mundo público para exploração e atividades compartilhadas. Progressão, inventário, economia, missões, classes e conquistas acompanham o jogador entre sessões. Cenas exclusivas de John (incluindo a casa e o diário) devem ocorrer em contexto pessoal sem interferir na vila compartilhada. **Ver GAME-014**, que contém regras de entrada, menu, carregamento, bloqueios e pendências técnicas.

O primeiro ciclo de formação inclui **A Primeira Lâmina** já definida acima e, futuramente, cadastro/treinamento na guilda, primeira classe e concessão persistente da **Insígnia da Guilda**. Só então são desbloqueados **Jogar com Amigos** e **Mundo Público**, também validados no servidor. As classes são **múltiplas por personagem**, com pontos de habilidade distribuídos individualmente e novas especializações registradas na **Carteira da Guilda**, sem escolha permanente obrigatória. **Ver GAME-015** para a distinção entre guilda, grupo, classes, conquista e desbloqueio.

**Ordem de trabalho:** a **Etapa 3 (padre, Árvore Ancestral e Madeira Ungida)** está **adiada temporariamente, não cancelada**. Prioridade atual é planejar e consolidar arquitetura do menu e acesso. Não declarar novos modos, classes, treinamento ou insígnia implementados nem publicar sem autorização.
