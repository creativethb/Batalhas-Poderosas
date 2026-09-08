---
id: "GAME-003"
nome: "Sistema de Locomoção, Dash e Duplo Pulo"
status: "CANONICO"
atualizado_por: "agente"
---

# Sistema de Locomoção, Dash e Duplo Pulo

## 1. Dash e Corrida Unificados
O sistema integra esquiva e aceleração no mesmo canal de comando:
- **Toque Rápido (< 0.22s):** Executa **Dash** direcional rápido no chão ou ar.
- **Segurar (> 0.22s):** Ativa **Corrida** (`WalkSpeed = 28` studs/s, FOV expandido para 78°).
- **Soltar:** Retorna à velocidade normal de caminhada (`WalkSpeed = 16`).

## 2. Duplo Pulo
- **Primeiro Pulo:** Física nativa de salto do Roblox.
- **Segundo Pulo:** Ativado no ar com animação customizada (`rbxassetid://124772337984809`), força de impulso `52` studs e emissão de partículas suaves nos pés.

## 3. Sistema de Foco / Lock-On
- **Ativação:** Tecla `R` (PC), `ButtonR1` (Gamepad) ou toque no botão de Foco da HUD Mobile.
- **Mecânica:** Trava a mira e retícula de combate no alvo inimigo mais próximo em até 60 studs.
- **Cancelamento:** Ao afastar mais de 72 studs ou ao reacionar o comando.
