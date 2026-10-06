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
atualizado_por: "codex"
data_atualizacao: "2026-10-06"
---

# Loop Principal e Progressão de Gameplay

## 1. Loop Central
O ciclo de jogo equilibra:
1. Exploração & Coleta.
2. Artesanato & Preparação.
3. Combate & Missões.

## 2. Fase 1: preparação de John

### Fluxo narrativo/gameplay em revisão
1. John procura Mestre Cedric buscando uma espada de madeira para treinamento.
2. Cedric não possui uma pronta e orienta John a reunir os materiais.
3. John vai a um estabelecimento da vila ligado ao trabalho ou fornecimento de madeira e obtém um pedaço de Madeira Comum.
4. John leva a Madeira Comum ao padre da vila e pede sua unção.
5. Depois do rito, o material passa a ser Madeira Ungida.
6. John obtém também o Galho da Árvore Sagrada / Madeira Sagrada, ligado à Árvore Sagrada e a Eldrin.
7. John retorna à oficina de Cedric com a Madeira Ungida e a Madeira Sagrada.
8. Cedric fabrica a espada de madeira destinada ao treinamento e entrega o Escudo de Madeira (**ITEM-007**) como cortesia única, sem custo adicional.
9. John equipa a espada e o escudo no inventário, pratica ataque, guarda frontal e esquiva, e prossegue com sua preparação.

### Pendências antes da implementação definitiva
- Definir qual estabelecimento fornece a Madeira Comum.
- Definir/identificar o padre da vila.
- Definir a ordem final entre a obtenção/unção da madeira comum e o Galho Sagrado.
- Criar ou revisar a ficha da Madeira Ungida.
- Revisar o nome e a receita definitiva da espada.
- Atualizar diálogos de Cedric, padre e Eldrin.
- Alterar no Roblox Studio a origem física da Madeira Comum.
- Validar o ciclo completo em Playtest.

> LEGADO ATUAL: a implementação que coloca Madeira Comum na mesa da Casa de John pertence ao fluxo antigo e não deve orientar novas decisões narrativas.

### Escudo integrado ao circuito atual — 06/10/2026

A primeira forja existente com Cedric entrega a espada e **um Escudo de Madeira de cortesia**. O diálogo explicita a cortesia; a explicação pode ser consultada novamente sem repetir a recompensa. A receita e os materiais atuais da espada foram preservados.

O escudo entra no inventário persistente e pode ser equipado na mão secundária, mantendo a espada na mão direita. John levanta a guarda, caminha com velocidade reduzida e bloqueia ataques comuns pela frente; ao soltar, retoma ataque e dash. Ver **ITEM-007**, **GAME-002** e **GAME-003**.

Essa adição já funciona no circuito implementado. A alteração da origem da Madeira Comum, a unção e a Madeira Ungida acima continuam como revisão pendente; esta entrega não implementa essas etapas.


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
