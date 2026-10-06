---
id: "GAME-003"
nome: "Sistema de Locomoção, Dash e Duplo Pulo"
status: "CANONICO"
relacionados:
  - "ITEM-007"
  - "GAME-002"
  - "GAME-004"
  - "BP-2026-005"
atualizado_por: "codex"
data_atualizacao: "2026-10-06"
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

- **Exploração:** mantém os comandos de pulo e dash/corrida acessíveis; o botão da arma permanece acima deles. Defesa também fica acessível quando o escudo está equipado, mesmo com a espada guardada.
- **Arma sacada:** ataque, defesa e foco se expandem em torno dos comandos principais. Ao guardar a arma, ataque e foco recolhem; Defesa permanece acessível se o escudo estiver equipado.
- **Dash/Corrida:** toque breve no botão executa dash; segurar ativa corrida; soltar encerra a corrida. O botão acompanha a posição do pulo.
- **Ergonomia:** o conjunto respeita a área segura da tela e usa separação maior entre os botões para reduzir toques acidentais em paisagem.
- **Leitura visual:** ícones próprios de ataque, escudo, foco, arma, dash e pulo substituem símbolos genéricos; as funções dos comandos permanecem iguais. O ícone do pulo é aplicado sobre o controle nativo, preservando sua área de toque.
- **Defesa:** implementada em 06/10/2026. Manter o botão existente pressionado levanta a guarda; soltar encerra. Exige escudo equipado (**ITEM-007**). No PC: botão direito do mouse ou C; ButtonL2 mapeado para controle. A guarda reduz a caminhada a 10 studs/s e impede dash/corrida. O Q continua exclusivo do dash.

A versão de desenvolvimento foi conferida no simulador de iPhone em paisagem, nos estados de exploração, arma sacada e arma guardada. O conjunto expandiu e recolheu sem sobreposição dos botões. O novo botão de pulo foi conferido visualmente no simulador, e um toque nele acionou o salto.


## 5. Música da Masmorra
- A exploração do primeiro piso usa música ambiente medieval de mistério, em loop, com volume moderado.
- Ao entrar no corredor de acesso da arena do Guardião do Piso 1, a música de exploração faz uma transição gradual para a faixa de tensão do chefe.
- As duas faixas são controladas separadamente para evitar cortes bruscos e não interferem no som ambiente da vila.


## 6. Validação da defesa — 06/10/2026

Play em PC e no simulador de **iPhone 17 Pro (874 × 402), paisagem**, conforme LandscapeSensor do jogo. O toque no botão Defesa foi mantido e liberado, com postura/velocidade corretas e caminhada de aproximadamente 12 studs em 1,2 s. A guarda funcionou com espada equipada, encerrou ao abrir a bolsa, desequipar ou morrer e voltou após renascimento.

A guarda conserva as animações de caminhada. A tela de PC permanece sem botões virtuais de combate. O simulador foi desativado ao terminar. Telefone e controle físicos não foram testados; ver **GAME-002**.
