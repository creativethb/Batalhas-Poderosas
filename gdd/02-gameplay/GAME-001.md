---
id: "GAME-001"
nome: "Loop Principal e Progressão de Gameplay"
status: "CANONICO"
relacionados:
  - "LORE-002"
  - "NPC-001"
  - "NPC-002"
  - "ITEM-003"
  - "BP-2026-002"
atualizado_por: "agente"
---

# Loop Principal e Progressão de Gameplay

## 1. Loop Central
O ciclo de jogo em Batalhas Poderosas equilibra três pilares fundamentais:
1. **Exploração & Coleta:** Vasculhar a vila, residências, florestas e minas em busca de recursos, diálogos com anciões e segredos.
2. **Artesanato & Preparação:** Levar materiais aos artesãos (como a Forja do Cedric) para confeccionar equipamentos aprimorados.
3. **Combate & Missões:** Enfrentar ameaças locais, patrulhar perímetros e desbravar portais para outras dimensões.

## 2. Fase 1: Despertar em Arkham
- **Spawn:** Jogador acorda no interior de sua casa na Colina Leste.
- **Objetivo 1:** Coletar 1 Madeira Comum na mesa principal.
- **Objetivo 2:** Ir até o bosque a oeste e conversar com o Ancião Eldrin para obter o Galho Sagrado.
- **Objetivo 3:** Ir até a oficina de Mestre Cedric na praça da vila e forjar a Espada de Madeira Sagrada.
- **Recompensa:** Espada de Madeira Sagrada equipada diretamente nas mãos de John com persistência total pós-morte.

## 3. Inicialização e Liberação do Jogador

A abertura do jogo foi reorganizada para impedir que o jogador veja o mundo sendo montado antes de estar pronto.

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

> Estes valores são **medições de teste local**, não metas canônicas de desempenho. Devem ser reavaliados conforme o projeto evoluir.

## 4. Estado Atual do Áudio

- IDs inválidos de sons locais que geravam avisos no console foram removidos, mantendo os objetos preparados para receber novos áudios.
- A música global da Vila de Arkham permanece em `SoundService`, pois pertence ao gameplay geral.
- O ID atual dessa música ainda apresenta falha de download e deve ser substituído futuramente por um áudio válido e autorizado.
