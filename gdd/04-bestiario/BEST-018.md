---
id: "BEST-018"
nome: "Grumelo"
funcao: "Terrestre ágil"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-011"
  - "ITEM-011"
  - "ITEM-012"
  - "ITEM-013"
  - "DNG-013"
  - "GAME-010"
  - "GAME-002"
imagem: "./assets/bestiario/BEST-018.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Grumelo

## Identidade e ocorrência

Inimigo comum do Piso 1, ativo no sorteio das salas Ruinas e PilaresArmadilha. Pode formar grupos homogêneos ou mistos com as outras quatro espécies; não substitui o Guardião.

## Ciclo de combate

Observar → aproximar → golpe simples ou sequência dupla → recuperar → recuar → reposicionar. Usa intervalos individuais e separação para evitar ataques perfeitamente sincronizados. Busca de caminho é usada quando encontra obstáculos.

O golpe simples atual usa o clip de ataque com a mão direita; o duplo repete esse ataque com pausa de 0,16 s, preservando preparação mais perceptível. A descrição anterior de alternar o braço esquerdo não corresponde ao refinamento de 10/10. O dano ocorre pelo contato da mão durante a janela real do movimento, uma vez por vítima por golpe, limitado por direção, alcance e paredes.

| Configuração provisória | Valor |
|---|---:|
| Vida | 88 |
| Aproximação / lateral / recuo | 12 / 6 / 7 studs/s |
| Golpe simples | 10 de dano |
| Sequência dupla | 8 por golpe |
| Probabilidade do duplo | 40% |
| Preparação simples / dupla | 0,32 / 0,62 s |
| Recuperação normal / duplo errado | 0,65 / 1,25 s |
| Intervalo após o ciclo | 1,7–2,6 s |

Valores ajustáveis em `PISO1_Grumelo.Config`. Escudo, espada e dano reutilizam o circuito existente; não foram criadas habilidades novas. Errar o duplo abre uma oportunidade de contra-ataque.

## Validação e pendências

Play com a Espada de Madeira real contra um, dois e três Grumelos; bloqueio por escudo, duplo errado e mistura com Vesplumes verificados. Modelo e juntas foram medidos em runtime. Acabamento visual, balanceamento definitivo e multiplayer real continuam pendentes.

## Modelo e animações

Modelo manual de 15 MeshParts corporais e 15 AnimationConstraints, Humanoid R15, altura 4,2 studs. Rig anterior preservado fora do Workspace. Locomoção usa os IDs padrão cadastrados; ataque nativo `127956831239286`, velocidade 1,5, com contato avaliado entre 0,43–0,76 s do tempo real do clip. Simples uma vez; duplo repete com pausa de 0,16 s.

Reação/derrota compostas em Transform/PreSimulation sem acumular C0; compensação visual dos pés durante o ataque não desloca a raiz física. Colisão concentrada na raiz e malhas consultáveis. Testes solo contra 1/2/3 criaturas, bloqueio, quatro golpes reais de John e derrota foram registrados. A medição do pé usa caixas, não vértices; terreno inclinado, multiplayer e especial de esporos ainda pendentes.

Prefab de execução em `ServerStorage.Dungeon_NPCs`; protótipos de edição ficam reservados fora do Workspace.

## Lore e espólios

> **Espólios implementados em 09/10/2026:** [ITEM-011 Esporos de Grumelo](../04-itens/ITEM-011.md), [ITEM-012 Fibra Fúngica](../04-itens/ITEM-012.md), [ITEM-013 Núcleo de Esporos](../04-itens/ITEM-013.md). Interação Examinar, sorteio único compartilhado com 20% de vazio forçado e coleta seletiva pelo sistema de GAME-011. Valores e identidades provisórios.



História própria e economia definitiva continuam a definir. Os materiais autorizados estão implementados e testados em Play local; multiplayer real, persistência entre servidores e validação final pendentes. Combate, rig e animações preservados; apenas a limpeza após derrota foi integrada à inspeção.

## Referência visual

> **Imagem publicada:** Grumelo, representação artística para o Bestiário.
> Arquivo: `./assets/bestiario/BEST-018.png`.

A ilustração representa a criatura no GDD; o modelo 3D atual no jogo permanece provisório.
