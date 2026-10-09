---
id: "BEST-021"
nome: "Cascudo"
funcao: "Terrestre com guarda direcional"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "DNG-013"
  - "GAME-010"
  - "GAME-002"
imagem: "./assets/bestiario/BEST-021.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-08"
---

# Cascudo

## Identidade e ocorrência

Quinta espécie comum do Piso 1, convivendo com Vesplume, Grumelo, Pedrino e Brisalto. Usa as placas já ligadas aos antebraços do modelo provisório.

## Ciclo e vulnerabilidade

Aproximar → levantar guarda → observar com giro limitado → baixar guarda → preparar pancada ou investida → recuperar exposto → reposicionar.

Somente a guarda completa protege o cone frontal de 110°. Nesse estado, recebe 30% do dano frontal normal; laterais e costas recebem dano integral. Levantar/baixar guarda, atacar e recuperar também recebem dano integral. Não há invulnerabilidade ou regeneração.

A pancada usa contato do antebraço. A investida captura a direção antes da preparação, avança fisicamente e consulta o volume do torso/ombro somente após deslocamento efetivo. Parede interrompe o avanço; dano não depende apenas de proximidade.

| Configuração provisória | Valor |
|---|---:|
| Vida | 99 |
| Aproximação / lateral / guarda | 9 / 5 / 3 studs/s |
| Guarda completa | 0,8–1,25 s |
| Cone protegido / dano frontal recebido | 110° / 30% |
| Giro máximo na guarda | 85°/s |
| Pancada / investida | 12 / 17 de dano |
| Preparação pancada / investida | 0,38 / 0,75 s |
| Recuperação pancada / investida acertada / errada | 0,75 / 0,85 / 1,4 s |
| Intervalo após o ciclo | 1,2–1,9 s |
| Investida máxima / velocidade | 3,8 studs / 13 studs/s |

Configuração em `PISO1_Cascudo.Config`. A redução utiliza um registro exclusivo desse Humanoid em `CombateDefesaService.RegistrarReducaoNPC`, removido na derrota/destruição; outros NPCs não recebem essa proteção.

## Validação e pendências

Espada real contra um, dois e três Cascudos. Na guarda, golpe de 22 causou 6,6 frontalmente e 22 por flanco/costas; fora da guarda, 22 frontalmente. Pancada e investida foram bloqueadas pelo escudo de John. Giro gradual, investida errada, parede, sala pequena e ausência de redução em outro NPC verificados. Multiplayer e acabamento visual continuam pendentes.

## Modelo e animações

Modelo e rig R15 preparados preservados; o acabamento artístico continua provisório. Idle 507766388, caminhada 507777826, corrida 507767714, pulo 507765000 e queda 507767968 são as animações padrão configuradas. Golpes, preparação, reação e derrota usam poses e transições Motor6D.C0, sem novos IDs publicados. Ter IDs configurados não equivale a validação visual de todas as trilhas.

Prefab de execução em `ServerStorage.Dungeon_NPCs`; protótipos de edição ficam reservados fora do Workspace.

## Lore e espólios

> **Planejamento de espólios (não implementado):** propostas consultáveis em [CATALOGO-ESPOLIOS-PROPOSTOS](../04-itens/CATALOGO-ESPOLIOS-PROPOSTOS.md), com fichas individuais ITEM-020 a ITEM-022. Não tratar propostas como loot ativo nem alterar a gameplay sem aprovação.



História própria, espólios e valores econômicos ainda não foram definidos. Esta ficha registra gameplay implementada, sem inventar origem narrativa ou recompensas.

## Referência visual reservada

> **Imagem pendente:** Cascudo.
> Arquivo reservado: `./assets/bestiario/BEST-021.png`.

O modelo atual é provisório. A imagem definitiva será anexada depois; não foi criada uma imagem fictícia nesta atualização.
