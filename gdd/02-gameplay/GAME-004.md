---
id: "GAME-004"
nome: "Sistema Imersivo de Diálogo e Câmera"
status: "CANONICO"
relacionados:
  - "NPC-001"
  - "NPC-002"
  - "GAME-001"
  - "GAME-003"
  - "BP-2026-005"
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Sistema Imersivo de Diálogo e Câmera Cinematográfica

## 1. Fluxo de Cena de Conversa
1. **Interação Inicial:** Jogador aciona `ProximityPrompt` ("Conversar") do NPC.
2. **Pausa Imediata:** O servidor interrompe a patrulha e rotinas do NPC ao aceitar a interação (`WalkSpeed = 0`, velocidades físicas zeradas).
3. **Aproximação Suave:** O cliente conduz John suavemente até o arco frontal do NPC (distância ideal ~4.8 studs).
4. **Alinhamento 100% Frontal:** Jogador e NPC giram e travam olhando diretamente um para o outro (`dot = 1.0000`).
5. **Bloqueio de Movimento:** John fica imóvel durante o diálogo (afundamento de WASD, pulo, dash e ataque via `ContextActionService` e atributo `EmDialogo`).
6. **Câmera Scriptable:** Interpolação suave (`TweenService`, 0.45s) para enquadramento over-the-shoulder focado no rosto do NPC (`FOV = 52°`).

## 2. HUD de diálogo — refinamento de 15/10/2026

- **Duas fases exclusivas:** primeiro fala do NPC; depois de confirmação por toque/clique/comando, a fala sai e entram as respostas. A escolha nunca é acionada automaticamente pelo toque que mudou de fase.
- Nome/cargo e fala em painel compacto próximo à margem inferior. Cada resposta tem placa própria dentro de uma moldura; não há algarismos decorativos 1/2/3, mas os atalhos existentes permanecem.
- PNGs próprios centralizados em `ReplicatedStorage.BP_DialogoVisual`. Identificação usa Fondamento; fala/respostas, Merriweather; instruções auxiliares, BuilderSans. Textos são elementos Roblox, medidos por largura/fonte/tamanho, com margens e fallback visual enquanto imagens carregam.
- Typewriter pode ser completado pelo jogador; a fase aguarda nova confirmação. Fechar permanece disponível com alvo de interação adequado.
- Câmera e bloqueios existentes foram preservados. No teste com Cedric no S25 Ultra, a cabeça ficou acima do painel. Isso não certifica o enquadramento de todos os NPCs nem os painéis próprios de serviços da Guilda.
- Respostas ficam numa fileira; alternativas excedentes ainda podem exigir **rolagem horizontal** e falas longas podem rolar. A proposta de encaixe sem rolagem ainda não foi aplicada. Não confundir ausência de múltiplas fileiras com ausência de rolagem.
- Prompt de diário/conversa acompanha o conteúdo. O diário foi reduzido de 204×48 para aproximadamente 136×48 pixels lógicos no mobile, sem alterar o acionamento de segurar/cancelar. Não aplicar essa largura fixa a todos os títulos.
- Gamepad mantém seleção e comandos de confirmar/fechar existentes. Layout TenFoot e fechamento por comando sintetizado foram conferidos; navegação em controle físico não foi certificada.

**Testes:** 120 estados de diálogo × 8 telas × 2 fases = 1.920 medições isoladas, sem falhas TextFits ou fala/opções simultâneas; Play real de Cedric/Eamon no PC e simulador S25 Ultra, quarta opção por arrasto, fechamento com câmera Custom/WalkSpeed 16 restaurados. Prompt testado com retenção curta cancelada e retenção completa abrindo o diário. A medição isolada não executa recompensas. Dispositivos físicos e revisão de cada NPC permanecem pendentes.

## 3. Encerramento Seguro
- Câmera retorna suavemente à posição normal.
- Todos os controles e velocidades de John são restaurados.
- NPC retoma sua rotina de patrulha.
