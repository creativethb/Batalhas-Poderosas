---
id: "BEST-018"
nome: "Grumelo"
funcao: "Terrestre ágil"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "DNG-013"
  - "GAME-010"
  - "GAME-002"
imagem: "./assets/bestiario/BEST-018.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-08"
---

# Grumelo

## Identidade e ocorrência

Inimigo comum do Piso 1, ativo no sorteio das salas Ruinas e PilaresArmadilha. Pode formar grupos homogêneos ou mistos com as outras quatro espécies; não substitui o Guardião.

## Ciclo de combate

Observar → aproximar → golpe simples ou sequência dupla → recuperar → recuar → reposicionar. Usa intervalos individuais e separação para evitar ataques perfeitamente sincronizados. Busca de caminho é usada quando encontra obstáculos.

O golpe simples usa o braço direito; a sequência dupla acrescenta o golpe esquerdo, com preparação mais perceptível. O dano ocorre pelo contato da mão durante a janela real do movimento, uma vez por vítima por golpe, limitado por direção, alcance e paredes.

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

Modelo e rig R15 preparados preservados; o acabamento artístico continua provisório. Idle 507766388, caminhada 507777826, corrida 507767714, pulo 507765000 e queda 507767968 são as animações padrão configuradas. Golpes, preparação, reação e derrota usam poses e transições Motor6D.C0, sem novos IDs publicados. Ter IDs configurados não equivale a validação visual de todas as trilhas.

Prefab de execução em `ServerStorage.Dungeon_NPCs`; protótipos de edição ficam reservados fora do Workspace.

## Lore e espólios

História própria, espólios e valores econômicos ainda não foram definidos. Esta ficha registra gameplay implementada, sem inventar origem narrativa ou recompensas.

## Referência visual reservada

> **Imagem pendente:** Grumelo.
> Arquivo reservado: `./assets/bestiario/BEST-018.png`.

O modelo atual é provisório. A imagem definitiva será anexada depois; não foi criada uma imagem fictícia nesta atualização.
