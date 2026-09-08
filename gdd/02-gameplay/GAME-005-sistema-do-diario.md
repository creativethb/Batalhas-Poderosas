---
id: "GAME-005"
nome: "Sistema do Diário de John"
status: "CANONICO"
relacionados:
  - "BP-2026-006"
  - "BP-2026-007"
  - "LORE-003"
  - "LOCAL-001"
  - "GAME-001"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "2026-09-08"
---

# Sistema do Diário de John

O Diário de John é simultaneamente **lore + narrativa + sistema de gameplay + inventário + progressão de desbloqueios**. Deve ser tratado no GDD Vivo como um sistema real do jogo, não apenas como texto de lore.

---

## 1. Aquisição

| Campo | Definição |
| :--- | :--- |
| **Onde** | Casa de John — Colina Leste, Vila de Arkham (LOCAL-001) |
| **Quando** | Início da introdução, antes ou junto da coleta da Madeira Comum |
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
