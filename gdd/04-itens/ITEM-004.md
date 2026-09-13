---
id: "ITEM-004"
nome: "Diário de John"
tipo: "Item Narrativo / Memória de Jornada"
raridade: "Único / Relíquia Pessoal"
status: "CANONICO"
localizacao: "Casa de John (Ponto Inicial de Spawn)"
relacionados:
  - "CANON-006"
  - "CANON-007"
  - "GAME-005"
  - "LORE-003"
  - "LOCAL-001"
imagem: "./assets/itens/ITEM-004.png"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "2026-09-08"
---

# Ficha de Item: Diário de John

## 1. Dados Básicos
- **ID do Item:** `ITEM-004` (Identificador no Script: `DiarioDeJohn` / `Diario`)
- **Nome no Inventário:** `Diário de John`
- **Tipo:** Item Narrativo & Ferramenta de Gameplay
- **Raridade:** Único / Relíquia Pessoal (Dourado / Nobre)
- **Local de Obtenção:** Encontrado sobre a mesa de repouso na Casa de John (`LOCAL-001`) no início da aventura.

---

## 2. Descrição & Aparência
Um caderno com encadernação em couro rústico escurecido, costura manual grossa e fecho simples de fivela de ferro. As páginas são de pergaminho amarelado e registram as anotações manuscritas em tinta fresca feitas pelo jovem soldado John.

---

## 3. Mecânicas de Gameplay & Inventário (GAME-005)
- **Aquisição Obrigatória:** Coletado no início do jogo via `ProximityPrompt` ou interação automática.
- **Slot de Inventário Permanente:** O item é transferido para o inventário do jogador e permanece fixo durante toda a progressão da campanha.
- **Indescartável:** Não pode ser vendido, descartado, trocado ou destruído.
- **Consulta em Runtime:** Quando selecionado/aberto fora de combate, aciona a interface imersiva do Diário (`HUD_Diario`), permitindo ao jogador ler as entradas desbloqueadas organizadas por capítulos.
- **Desbloqueio Progressivo de Entradas:** Cada avanço relevante na campanha principal libera novos registros com indicador visual de novidade (*não lido*).
