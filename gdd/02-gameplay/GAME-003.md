---
id: "GAME-003"
nome: "Sistema de Locomoção, Dash e Duplo Pulo"
status: "CANONICO"
relacionados:
  - "GAME-002"
  - "GAME-004"
  - "CANON-005"
atualizado_por: "codex"
data_atualizacao: "2026-09-20"
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

## 4. HUD Mobile e Estados de Combate

- **Exploração:** mantém os comandos de pulo e dash/corrida acessíveis; o botão da arma permanece acima deles.
- **Arma sacada:** ataque, defesa e foco se expandem em torno dos comandos principais. Ao guardar a arma, o conjunto recolhe para o estado de exploração.
- **Dash/Corrida:** toque breve no botão executa dash; segurar ativa corrida; soltar encerra a corrida. O botão acompanha a posição do pulo.
- **Ergonomia:** o conjunto respeita a área segura da tela e usa separação maior entre os botões para reduzir toques acidentais em paisagem.
- **Leitura visual:** ícones próprios de ataque, escudo, foco, arma e dash substituem símbolos genéricos; as funções dos comandos permanecem iguais.
- **Defesa:** o botão está visualmente preparado para a mecânica de defesa futura; sua ação ainda não foi implementada.

A versão de desenvolvimento foi conferida no simulador de iPhone em paisagem, nos estados de exploração, arma sacada e arma guardada. O conjunto expandiu e recolheu sem sobreposição dos botões.
