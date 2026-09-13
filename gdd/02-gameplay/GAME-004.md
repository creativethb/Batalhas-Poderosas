---
id: "GAME-004"
nome: "Sistema Imersivo de Diálogo e Câmera"
status: "CANONICO"
atualizado_por: "agente"
---

# Sistema Imersivo de Diálogo e Câmera Cinematográfica

## 1. Fluxo de Cena de Conversa
1. **Interação Inicial:** Jogador aciona `ProximityPrompt` ("Conversar") do NPC.
2. **Pausa Imediata:** O servidor congela a patrulha e rotinas do NPC no mesmo milissegundo (`WalkSpeed = 0`, velocidades físicas zeradas).
3. **Aproximação Suave:** O cliente conduz John suavemente até o arco frontal do NPC (distância ideal ~4.8 studs).
4. **Alinhamento 100% Frontal:** Jogador e NPC giram e travam olhando diretamente um para o outro (`dot = 1.0000`).
5. **Bloqueio de Movimento:** John fica imóvel durante o diálogo (afundamento de WASD, pulo, dash e ataque via `ContextActionService` e atributo `EmDialogo`).
6. **Câmera Scriptable:** Interpolação suave (`TweenService`, 0.45s) para enquadramento over-the-shoulder focado no rosto do NPC (`FOV = 52°`).

## 2. HUD de Diálogo Medieval
- **Cabeçalho:** Nome em destaque (`Antique`) e Cargo/Subtítulo (`GothamBold`).
- **Texto:** Animação typewriter suave (acelerável com toque/clique/tecla).
- **Controle de Gamepad / Console:** Suporte a navegação por D-Pad / analógico com `SelectionImageObject` customizado (sem caixa branca ofuscante), `ButtonA`/`ButtonX` para avançar/confirmar e `ButtonB` para fechar.
- **Botão Fechar:** Ícone de `"X"` nítido.
- **Branching de Opções:** Suporte a múltiplas escolhas, forja de itens e avanço de missões.

## 3. Encerramento Seguro
- Câmera retorna suavemente à posição normal.
- Todos os controles e velocidades de John são restaurados.
- NPC retoma sua rotina de patrulha.
