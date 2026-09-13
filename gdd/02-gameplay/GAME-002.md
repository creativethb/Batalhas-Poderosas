---
id: "GAME-002"
nome: "Sistema de Combate e Combos"
status: "CANONICO"
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
