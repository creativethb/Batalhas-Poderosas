---
id: "BEST-019"
nome: "Pedrino"
funcao: "Terrestre de ataques pesados"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-011"
  - "ITEM-014"
  - "ITEM-015"
  - "ITEM-016"
  - "DNG-013"
  - "GAME-010"
  - "GAME-002"
imagem: "./assets/bestiario/BEST-019.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-09"
---

# Pedrino

## Identidade e ocorrência

Inimigo comum terrestre do Piso 1, ativo no mesmo sorteio das cinco espécies. Modelo provisório construído com primitivas, preservado para substituição artística futura.

## Ciclo e ataques

Aproximação lenta → preparação visível → pancada frontal ou impacto no chão → recuperação longa → reposicionamento.

A pancada usa contato da mão direita. O impacto no chão projeta um ponto 3,2 studs à frente sobre piso colidível e atinge uma pequena área cilíndrica, com limite vertical e checagem de parede. Sem piso não há impacto. Dano é aplicado uma vez por personagem pelo serviço de combate existente.

| Configuração provisória | Valor |
|---|---:|
| Vida | 132 |
| Aproximação / lateral e recuo | 7 / 4 studs/s |
| Alcance para iniciar | 3,8 studs |
| Pancada / impacto no chão | 18 / 24 de dano |
| Probabilidade do impacto | 35% |
| Preparação pancada / impacto | 0,85 / 1,35 s |
| Recuperação pancada / impacto | 1,15 / 1,9 s |
| Intervalo após o ciclo | 2,5–3,8 s |
| Raio do impacto / limite vertical | 3,6 / 4,2 studs |

Configuração em `PISO1_Pedrino.Config`. Recebe dano normalmente durante o ataque pesado, mas esse ciclo não é cancelado por cada golpe recebido. Não possui invulnerabilidade, regeneração ou defesa paralela.

## Validação e pendências

Espada real contra um, dois e três; pancada de 18 e impacto de 24; ambos bloqueados pelo escudo; saída da área e ausência de piso sem dano. Sorteio misto e alinhamento do rig verificados. Dash foi representado por reposicionamento controlado. Apreciação estética, testes dedicados de obstáculos e multiplayer permanecem pendentes.

## Modelo e animações

Modelo e rig R15 preparados preservados; o acabamento artístico continua provisório. Idle 507766388, caminhada 507777826, corrida 507767714, pulo 507765000 e queda 507767968 são as animações padrão configuradas. Golpes, preparação, reação e derrota usam poses e transições Motor6D.C0, sem novos IDs publicados. Ter IDs configurados não equivale a validação visual de todas as trilhas.

Prefab de execução em `ServerStorage.Dungeon_NPCs`; protótipos de edição ficam reservados fora do Workspace.

## Lore e espólios

> **Espólios implementados em 09/10/2026:** [ITEM-014 Fragmento de Rocha](../04-itens/ITEM-014.md), [ITEM-015 Cascalho Mineral](../04-itens/ITEM-015.md), [ITEM-016 Coração de Pedra](../04-itens/ITEM-016.md). Interação Examinar, sorteio único compartilhado com 20% de vazio forçado e coleta seletiva pelo sistema de GAME-011. Valores e identidades provisórios.



História própria e economia definitiva continuam a definir. Os materiais autorizados estão implementados e testados em Play local; multiplayer real, persistência entre servidores e validação final pendentes. Combate, rig e animações preservados; apenas a limpeza após derrota foi integrada à inspeção.

## Referência visual reservada

> **Imagem pendente:** Pedrino.
> Arquivo reservado: `./assets/bestiario/BEST-019.png`.

O modelo atual é provisório. A imagem definitiva será anexada depois; não foi criada uma imagem fictícia nesta atualização.
