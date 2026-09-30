---
id: "GAME-001"
nome: "Loop Principal e Progressão de Gameplay"
status: "CANONICO"
relacionados:
  - "LORE-002"
  - "NPC-001"
  - "NPC-002"
  - "NPC-014"
  - "ITEM-001"
  - "ITEM-002"
  - "ITEM-003"
  - "DOS-004"
  - "BP-2026-002"
atualizado_por: "ChatGPT"
data_atualizacao: "2026-09-30"
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
8. Cedric fabrica a espada de madeira destinada ao treinamento.
9. John prossegue com sua preparação.

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
