---
id: "LORE-003"
nome: "Diário de John — Registros da Jornada"
status: "CANONICO"
relacionados:
  - "BP-2026-006"
  - "BP-2026-007"
  - "GAME-005"
  - "LORE-001"
  - "LORE-002"
  - "LORE-004"
  - "LOCAL-001"
  - "NPC-001"
  - "NPC-002"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "2026-09-08"
---

# O Diário de John

> *Um caderno de capa escura, costura grossa e páginas levemente amareladas. Encontrado em Arkham no início da aventura. Nas primeiras páginas, a tinta ainda está fresca.*

---

## Sobre o Diário

O Diário de John é um elemento de **gameplay e narrativa pessoal**. Existe fisicamente no mundo do jogo, é coletado pelo jogador, entra no inventário e pode ser consultado durante a aventura.

Escrito em primeira pessoa — com a voz e as percepções de John. Um registro pessoal, não uma enciclopédia.

**Diferença fundamental:**
- O Diário responde: *"O que está acontecendo comigo?"*
- A Lore do universo responde: *"O que aconteceu neste mundo?"*

Para as regras de sistema (aquisição, inventário, consulta, desbloqueio), ver `gdd/02-gameplay/GAME-005-sistema-do-diario.md`.

> 🟡 **PROVISÓRIO:** A localização exata onde o Diário é encontrado (ex: Casa de John, Colina Leste) não deve ser tratada como cânone definitivo até nova decisão.

---

## Estrutura de Campos

| Campo | Descrição |
| :--- | :--- |
| **ID** | Identificador único (DIARIO-CAP[N]-[XXX]) |
| **Capítulo** | Grande fase narrativa |
| **Título** | Nome descritivo da entrada |
| **Momento** | Ponto da campanha |
| **Local** | Onde John estava ao escrever |
| **Evento Gatilho** | O que desbloqueou esta entrada |
| **Condição** | Regra exata de desbloqueio |
| **Obrigatoriedade** | OBRIGATÓRIO / OPCIONAL |
| **Estado** | BLOQUEADO / DESBLOQUEADO / LIDO |
| **Campanha** | Missão ou arco relacionado |
| **Status** | CANONICO / EM_DESENVOLVIMENTO / PLANEJADO |
| **Continuidade** | Notas de consistência com outros documentos |

---

## Capítulo I — As Raízes de Arkham

### DIARIO-CAP1-001 — Primeira Página

| Campo | Valor |
| :--- | :--- |
| **Momento** | Início da gameplay — antes de qualquer ação |
| **Local** | Arkham — localização exata provisória |
| **Evento Gatilho** | O jogador encontra o Diário no mundo (automático) |
| **Condição** | Desbloqueado ao adquirir o Diário |
| **Obrigatoriedade** | OBRIGATÓRIO |
| **Estado** | DESBLOQUEADO |
| **Campanha** | Prólogo |
| **Status** | CANONICO |
| **Continuidade** | Estabelece: John está em Arkham, Arkham ainda vive em paz relativa, a guerra existe em outras regiões, John sabe que não está preparado. Não revela detalhes biográficos. Não explica o universo inteiro. |

**Texto:**
> *Arkham ainda respira.*
>
> *Lá fora, do lado de fora das muralhas, a guerra já chegou em outros lugares. As notícias chegam com os viajantes — sempre mais sombrias, sempre mais próximas. Todos aqui sabem. Ninguém finge que não sabe.*
>
> *Sou o único soldado desta vila. Isso não é glória — é uma responsabilidade que pesa mais do que qualquer armadura.*
>
> *Ainda não estou pronto. Preciso me preparar. Cada dia que passa é um dia a menos antes que o que chegou a outros lugares chegue aqui também.*
>
> *Começo hoje.*

---

### DIARIO-CAP1-002 — A Bênção de Eldrin

| Campo | Valor |
| :--- | :--- |
| **Momento** | Após receber a Madeira Sagrada do Ancião Eldrin |
| **Local** | Árvore Sagrada — Santuário Oeste (LOCAL-004) |
| **Evento Gatilho** | Conclusão do diálogo com NPC-002 (Ancião Eldrin) |
| **Condição** | Após receber ITEM-002 (Galho Sagrado / Madeira Sagrada) |
| **Obrigatoriedade** | OBRIGATÓRIO |
| **Estado** | BLOQUEADO |
| **Campanha** | MISSAO-001 — A Primeira Lâmina Sagrada |
| **Status** | CANONICO |
| **Continuidade** | Reforça o peso simbólico da Madeira Sagrada (ITEM-002). Desenvolve Eldrin (NPC-002). Introduz a ideia de que a força vem da intenção, não apenas do material. |

**Texto:**
> *Eldrin tem olhos que parecem ver além das árvores.*
>
> *Quando me entregou o galho, disse que a madeira desta árvore nunca quebra — não a madeira, mas a intenção de quem a empunha.*
>
> *Não sei se sou digno disso. Mas a vila precisa de alguém que tente.*

---

### DIARIO-CAP1-003 — A Lâmina de Cedric

| Campo | Valor |
| :--- | :--- |
| **Momento** | Após forjar a Espada de Madeira Sagrada |
| **Local** | Oficina do Cedric — Praça Sul (LOCAL-002) |
| **Evento Gatilho** | Forja concluída na bigorna de Mestre Cedric (NPC-001) |
| **Condição** | Após receber ITEM-003 (Espada de Madeira Sagrada) |
| **Obrigatoriedade** | OBRIGATÓRIO |
| **Estado** | BLOQUEADO |
| **Campanha** | MISSAO-001 — A Primeira Lâmina Sagrada |
| **Status** | CANONICO |
| **Continuidade** | Confirma as propriedades incomuns da espada (ITEM-003). Caracteriza Cedric (NPC-001) como homem de ação, não de palavras. |

**Texto:**
> *Cedric é um homem de poucas palavras e muitas faíscas.*
>
> *Quando a lâmina saiu da bacia de têmpera, ele apenas assentiu. Para ele, era trabalho. Para mim, era o início de algo que ainda não entendo completamente.*
>
> *A espada pesa menos do que deveria. Brilha um pouco no escuro. Isso não é normal.*
>
> *Mas Arkan precisa de coisas que não são normais agora.*

---

## Entradas Planejadas

| ID | Título | Condição | Status |
| :--- | :--- | :--- | :--- |
| DIARIO-CAP1-004 | Primeiro Confronto | Primeiro combate real — evento a definir | PLANEJADO |
| DIARIO-CAP1-005 | O Teletransporte | Confronto culminante — mecânica a definir | PLANEJADO |
| DIARIO-CAP2-001+ | Registros do Multiverso | Exploração das dimensões | PLANEJADO |
