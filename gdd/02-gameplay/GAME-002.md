---
id: "GAME-002"
nome: "Sistema de Combate e Combos"
status: "CANONICO"
relacionados:
  - "ITEM-003"
  - "GAME-001"
  - "CANON-005"
atualizado_por: "agente"
---

# Sistema de Combate e Combos de Espada

## 1. Arquitetura de Golpes (Combo de 5 Hits)
O combate corpo a corpo utiliza uma sequência encadeada de 5 animações fluidas na prioridade `Action`:
- **Hit 1:** `rbxassetid://132874711732733`
- **Hit 2:** `rbxassetid://102975027054676`
- **Hit 3:** `rbxassetid://129511831949775`
- **Hit 4:** `rbxassetid://93640942970410`
- **Hit 5:** `rbxassetid://96266670191454`

## 2. Regras de Encadeamento & Reset
- Cada ativação avança para o golpe seguinte (`1 → 2 → 3 → 4 → 5 → 1`).
- **Cooldown entre Golpes:** `0.42s`.
- **Tempo de Reset de Combo:** `1.15s` de inatividade reinicia o ciclo no Hit 1.
- **Impulso Tático:** Golpes desferidos em repouso geram um leve avanço frontal no personagem.

## 3. Hitbox & Validação de Dano
- **Detecção Espacial:** Varredura em tempo real (`GetPartBoundsInBox`) em torno da lâmina durante a janela ativa do golpe (0.28s).
- **Validação no Servidor:** Remote `ProcessarDano` no `GerenciadorCombateServer` com proteção anti-autodano e efeitos visuais de faíscas no ponto de impacto.

## 4. Postura Natural e Braço Livre
- A ferramenta neutraliza a postura rígida nativa do Roblox (`507768375`).
- O braço de John permanece solto e relaxado para baixo, balançando de forma natural durante a caminhada e corrida.


## 6. Autômatos da Masmorra
Os lacaios do primeiro piso usam o avatar R15 padrão do golem comum e o Guardião do Piso 1 usa o avatar R15 próprio do chefe. Ambos usam somente as animações R15 padrão do Roblox para espera, caminhada e corrida; não há marcha procedural. Os lacaios usam juntas Motor6D R15 nativas para permanecerem firmes após o despertar, sem travar a animação.

- Os lacaios usam perseguição direta ou pathfinding, ataque por proximidade e velocidade normal de 13 studs/s.
- O lacaio alterna entre um soco fraco e um golpe concentrado. As duas animações funcionam sem arma nesta fase e poderão ser reutilizadas quando o armamento do autômato for criado.
- O Guardião é selecionado pelo gerador pelo prefab `Golem_Pedra`, antes do modelo antigo `Chefe`, e mantém IA própria, 450 pontos de vida, alcance e dano distintos.
- O Guardião do Piso 1 empunha uma clava fixada na mão direita. Seu ataque atual usa uma única animação de clava, sincronizada com a janela de dano do combate e orientada para o alvo antes do golpe.

## 7. Guarda da Entrada da Masmorra
Armand e Leofric são os guardas estáticos posicionados nas laterais da entrada do Mausoléu, sem bloquear o acesso ao portal. Ambos permanecem em espera com a animação R15 padrão do Roblox; Armand segura uma lança na mão direita e Leofric na mão esquerda. Não patrulham nem participam de combate.

- Interação: `E` para conversar.
- Avisos: a masmorra exige preparo, os autômatos patrulham o primeiro piso e o Guardião protege a passagem adiante.

## 8. Mestre Cedric da Oficina
O Mestre Cedric usa um avatar R15 estático, escalado para manter a altura do avatar anterior e posicionado de frente para o balcão da oficina. Ele não patrulha e usa somente a animação padrão R15 de espera. Ao iniciar uma conversa, volta-se brevemente para o jogador e depois retorna à posição de trabalho.

- A interação de forja existente e o identificador de diálogo do Cedric são preservados.
- O nome não é exibido sobre a cabeça do personagem.
