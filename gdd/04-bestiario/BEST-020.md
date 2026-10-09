---
id: "BEST-020"
nome: "Brisalto"
funcao: "Terrestre saltitante"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-011"
  - "ITEM-017"
  - "ITEM-018"
  - "ITEM-019"
  - "DNG-013"
  - "GAME-010"
  - "GAME-002"
imagem: "./assets/bestiario/BEST-020.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-09"
---

# Brisalto

## Identidade e ocorrência

Inimigo comum do Piso 1 com mobilidade por saltos curtos. Integra grupos homogêneos e mistos das salas comuns. Aparência de primitivas preservada para refinamento posterior.

## Ciclo e ataques

Aproximar → preparar → golpe curto ou investida saltitante → aterrissar/recuperar → recuar ou reposicionar. Saltos laterais se alternam com movimentação terrestre.

O golpe curto consulta contato da mão. A investida captura a direção antes da preparação e mantém a trajetória no ar. Dano ocorre após confirmar aterrissagem, perto do ponto real, uma vez por vítima e sem atravessar paredes. Piso ausente, desnível excessivo, obstáculos ou outro inimigo no caminho podem impedir o salto. Varredura durante o movimento interrompe a velocidade horizontal diante de parede.

| Configuração provisória | Valor |
|---|---:|
| Vida | 66 |
| Aproximação / lateral | 13 / 6 studs/s |
| Golpe / investida | 10 / 14 de dano |
| Preparação golpe / investida | 0,32 / 0,7 s |
| Recuperação normal / investida errada | 0,65 / 1,25 s |
| Intervalo após o ciclo | 1,8–2,8 s |
| Investida máxima / duração prevista | 5,5 studs / 0,32 s |
| Salto de posição / intervalo mínimo entre saltos | 2,2 studs / 2,8 s |

Valores em `PISO1_Brisalto.Config`. Recebe dano durante os saltos. Ambos os ataques respeitam o escudo existente; não há invulnerabilidade ou teletransporte.

## Validação e pendências

Espada real contra um, dois e três Brisaltos; golpes, bloqueio, saída lateral, parede, limite territorial e sala pequena verificados. Investida errada manteve direção e abriu recuperação. Multiplayer, dificuldade final e revisão artística quadro a quadro ainda não foram validados.

## Modelo e animações

Modelo e rig R15 preparados preservados; o acabamento artístico continua provisório. Idle 507766388, caminhada 507777826, corrida 507767714, pulo 507765000 e queda 507767968 são as animações padrão configuradas. Golpes, preparação, reação e derrota usam poses e transições Motor6D.C0, sem novos IDs publicados. Ter IDs configurados não equivale a validação visual de todas as trilhas.

Prefab de execução em `ServerStorage.Dungeon_NPCs`; protótipos de edição ficam reservados fora do Workspace.

## Lore e espólios

> **Espólios implementados em 09/10/2026:** [ITEM-017 Pena de Correnteza](../04-itens/ITEM-017.md), [ITEM-018 Essência de Brisa](../04-itens/ITEM-018.md), [ITEM-019 Cristal de Corrente Ascendente](../04-itens/ITEM-019.md). Interação Examinar, sorteio único compartilhado com 20% de vazio forçado e coleta seletiva pelo sistema de GAME-011. Valores e identidades provisórios.



História própria e economia definitiva continuam a definir. Os materiais autorizados estão implementados e testados em Play local; multiplayer real, persistência entre servidores e validação final pendentes. Combate, rig e animações preservados; apenas a limpeza após derrota foi integrada à inspeção.

## Referência visual reservada

> **Imagem pendente:** Brisalto.
> Arquivo reservado: `./assets/bestiario/BEST-020.png`.

O modelo atual é provisório. A imagem definitiva será anexada depois; não foi criada uma imagem fictícia nesta atualização.
