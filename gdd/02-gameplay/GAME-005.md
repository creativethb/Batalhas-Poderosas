---
id: "GAME-005"
nome: "Sistema do Diário de John"
status: "CANONICO"
relacionados:
  - "BP-2026-006"
  - "BP-2026-007"
  - "GAME-007"
  - "LORE-003"
  - "LOCAL-001"
  - "GAME-001"
  - "ITEM-004"
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Sistema do Diário de John

O Diário de John é simultaneamente **lore + narrativa + sistema de gameplay + inventário + progressão de desbloqueios**. Deve ser tratado no GDD Vivo como um sistema real do jogo, não apenas como texto de lore.

---

## 1. Aquisição

| Campo | Definição |
| :--- | :--- |
| **Onde** | Casa de John — Colina Leste, Vila de Arkham (LOCAL-001) |
| **Quando** | Início da jornada na casa; a Madeira Comum agora é coletada atrás da igreja (GAME-001) |
| **Como** | Jogador interage com o Diário no cenário (ProximityPrompt ou pickup automático) |
| **Resultado** | Diário entra no inventário do jogador permanentemente |

---

## 2. Inventário

- O Diário é colocado no inventário após aquisição.
- Permanece com o jogador durante toda a progressão.
- O jogador pode selecioná-lo e consultá-lo a qualquer momento fora de combate.
- Não pode ser descartado nem perdido.

---

## 3. Consulta

| Campo | Definição |
| :--- | :--- |
| **Abertura** | Seleção via inventário / atalho de hotbar / botão de menu |
| **Organização** | Entradas organizadas por Capítulo → ordem cronológica de desbloqueio |
| **Identificação de novo conteúdo** | Entradas recém-desbloqueadas marcadas com indicador visual (ex: ponto dourado, página marcada) |
| **Diferenciação lido/novo** | Conteúdo já lido sem marcação; conteúdo novo destacado até o jogador abrir a entrada |

---

## 4. Desbloqueio de Entradas

Cada entrada do Diário é desbloqueada por um evento específico da campanha.

### Campos obrigatórios por entrada

| Campo | Descrição |
| :--- | :--- |
| **ID da Entrada** | Identificador único (ex: DIARIO-CAP1-001) |
| **Capítulo** | Grande fase narrativa correspondente |
| **Título** | Nome descritivo da entrada |
| **Momento da História** | Ponto da campanha em que ocorre |
| **Localização** | Onde John estava ao escrever |
| **Evento que Desbloqueia** | Gatilho de gameplay (missão, diálogo, coleta, etc.) |
| **Condição de Desbloqueio** | Regra exata (ex: "após concluir MISSAO-001") |
| **Texto Integral** | Conteúdo em primeira pessoa, voz de John |
| **Obrigatoriedade** | `OBRIGATÓRIO` ou `OPCIONAL` |
| **Estado de Leitura** | `BLOQUEADO` / `DESBLOQUEADO` / `LIDO` |
| **Relação com Missão/Objetivo** | ID da missão ou arco relacionado |
| **Status de Canonização** | `CANONICO` / `EM_DESENVOLVIMENTO` / `PLANEJADO` |
| **Observações de Continuidade** | Notas de consistência com outros documentos do GDD |

---

## 5. Progressão por Capítulos

A estrutura de desbloqueio acompanha:

```
Capítulo → Região/Mundo → Acontecimentos → Entradas do Diário
```

Os nomes e a quantidade de capítulos podem mudar conforme o desenvolvimento avança.

---

## 6. Regras de Design

- O jogador nunca recebe toda a história de uma vez.
- O Diário começa com poucas entradas — suficientes para situar, não para revelar.
- Entradas obrigatórias são desbloqueadas automaticamente por eventos da campanha.
- Entradas opcionais podem depender de exploração, diálogos extras ou descobertas.
- O sistema deve suportar marcação de "novo conteúdo" para incentivar o jogador a abrir o Diário.

---

## 7. Entradas Canônicas Atuais

Ver `gdd/01-lore/LORE-003-diario-de-john.md` para o conteúdo integral das entradas registradas.

| ID | Título | Desbloqueio | Status |
| :--- | :--- | :--- | :--- |
| DIARIO-CAP1-001 | O Dia em que Acordei | Início do jogo (automático) | CANONICO |
| DIARIO-CAP1-002 | A Bênção de Eldrin | Após diálogo com NPC-002 | CANONICO |
| DIARIO-CAP1-003 | A Lâmina de Cedric | Após forja concluída com NPC-001 | CANONICO |
| DIARIO-CAP1-004 | Primeiro Confronto | Primeiro combate nos arredores de Arkham | PLANEJADO |
| DIARIO-CAP1-005 | O Teletransporte | Confronto com força superior / banimento | PLANEJADO |
| DIARIO-CAP2+ | Registros do Multiverso | Exploração de dimensões desconhecidas | PLANEJADO |

---

## 8. Integração com a Primeira Masmorra

A **vitória no primeiro andar** e a **primeira experiência completa de John na masmorra** já estão conectadas ao sistema de Diário.

O gatilho de gameplay está implementado no fluxo de conclusão do Piso 01 (`DNG-006`). O texto literário definitivo da entrada deve permanecer centralizado em `LORE-003`; este documento registra apenas a integração funcional, evitando duplicar conteúdo narrativo.

---

## 9. Interface independente — implementação de 13/10/2026

O leitor atual é `HUD_Diario`, separado da bolsa. Interagir com o livro físico, selecionar o item em Tudo/Especiais ou usar J abre o mesmo sistema existente. A categoria Diário e o leitor embutido no alforge foram removidos. Conteúdo, remotos, leitura e desbloqueios continuam no BancoDeDiario/GerenciadorDiarioServer.

`SistemaDiario.NarracaoConfig` associa `DIARIO-CAP1-001` ao áudio **90096381155243**. Pausa, retomada, reinício e volume são locais; fechar ou trocar de página interrompe a narração. Páginas bloqueadas não reproduzem áudio. O ID anterior 127165247009922 era dos pensamentos, não a gravação do registro. Os demais áudios ainda dependem de fornecimento.

Mapa e carteira são interfaces independentes (GAME-007/GAME-012), coordenadas com as janelas existentes por BP_UIState; o diário não precisa abrir a bolsa para ser consultado.

**Testes registrados:** interação E, leitor independente, pausa/reinício, página bloqueada, leitura persistente e recarga de perfil em memória; layouts estreito/paisagem simulados. O áudio corrigido carregou no Studio com duração de 19,879 s; o Play completo de reprodução ocorreu antes da troca de ID, não foi repetido para essa alteração pontual. Dispositivos físicos e reconexão publicada permanecem pendentes.
