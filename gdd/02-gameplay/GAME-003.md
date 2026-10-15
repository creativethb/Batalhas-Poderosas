---
id: "GAME-003"
nome: "Sistema de Locomoção, Dash e Duplo Pulo"
status: "CANONICO"
relacionados:
  - "ITEM-007"
  - "GAME-002"
  - "GAME-004"
  - "BP-2026-005"
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
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

## 4. HUD mobile e estados de combate

- Exploração: pulo, dash/corrida e sacar. Com arma sacada, o leque revela ataque, defesa e foco; defesa depende do escudo. Fechar interface exclusiva restaura os controles anteriores, sem duplicá-los.
- Refinamento de 11/10: círculos de 64 px e separação entre centros de 78 px; foco e defesa alinhados, defesa próxima do ataque, sacar acima do ataque, pulo/dash à esquerda. Layout estreito tem alternativa em duas colunas. Medidas são lógicas e adaptáveis, não pixels físicos universais.
- Seis ícones próprios individuais, centralizados em BP_ControlesVisuais; não são recortes reposicionados de um atlas.
- Uma única rotina controla o layout móvel. DashController acompanha TouchGui/JumpButton nativos que aparecem tardiamente, sem exigir que o pulo esteja visível e sem criar duplicatas.
- Defesa mantém as regras de GAME-002: segurar/soltar, caminhada a 10 studs/s e exclusão de dash/corrida. A implementação atual de parry está descrita separadamente naquela ficha.

Testes em simulador verificaram expansão/recolhimento, alinhamento, ocultação durante bolsa e estabilidade das posições. A tarja remanescente do Scriptorium foi corrigida no controlador próprio. Telefone físico, ergonomia real e controles específicos da besta permanecem pendentes.

### Inicialização do dash — 15/10/2026

O aviso antecipado de JumpButton ausente foi corrigido para acompanhar a chegada do controle nativo e só avisar, se necessário, após início efetivo da gameplay. Play ficou 44,77 s no menu sem aviso falso e exibiu um dash de 64×64 ao entrar. Não houve alteração da física de locomoção.

O aviso FoundationProvider/UIBlox é distinto: foi reproduzido também em Place vazio, sem scripts do projeto, em PC/mobile. A origem exata no cliente Roblox e a homologação fora do Studio continuam pendentes; não foi ocultado nem declarado resolvido.

## 5. Música da Masmorra
- A exploração do primeiro piso usa música ambiente medieval de mistério, em loop, com volume moderado.
- Ao entrar no corredor de acesso da arena do Guardião do Piso 1, a música de exploração faz uma transição gradual para a faixa de tensão do chefe.
- As duas faixas são controladas separadamente para evitar cortes bruscos e não interferem no som ambiente da vila.


## 6. Validação da defesa — 06/10/2026

Play em PC e no simulador de **iPhone 17 Pro (874 × 402), paisagem**, conforme LandscapeSensor do jogo. O toque no botão Defesa foi mantido e liberado, com postura/velocidade corretas e caminhada de aproximadamente 12 studs em 1,2 s. A guarda funcionou com espada equipada, encerrou ao abrir a bolsa, desequipar ou morrer e voltou após renascimento.

A guarda conserva as animações de caminhada. A tela de PC permanece sem botões virtuais de combate. O simulador foi desativado ao terminar. Telefone e controle físicos não foram testados; ver **GAME-002**.
