# 🔗 MAPA DE RELAÇÕES & GRAFO SEMÂNTICO — BATALHAS PODEROSAS

> **FUNÇÃO:** Mapear o impacto sistêmico e narrativo entre Personagens, Locais, Itens, Gameplay, Cânone, Lore e Dossiês. Qualquer alteração em um nó requer revisão nos nós conectados.
> **REGRAS:** Este documento é o grafo de referência. O mesmo cruzamento está espelhado no campo `relacionados:` do frontmatter de cada ficha em `/gdd/` (renderizado ao vivo pelo Códice v2.8.0 no `index.html`). Ao editar um lado, edite o outro.
> **ÚLTIMA ATUALIZAÇÃO:** 14/09/2026 — grafo expandido para 100% das entidades canônicas (NPC-000 a 013, ITEM-001 a 004, LOCAL-001 a 009, LORE-001 a 006, GAME-001 a 006, CANON-001 a 008, DOS-001 a 003).

---

## 0. Legenda de Estados

| Tag | Estado | Significado |
| :--- | :--- | :--- |
| `[🟢 CANÔNICO]` | Canônico | Fato oficial aprovado. Imutável sem ordem direta. |
| `[🟡 EM CONSTRUÇÃO]` | Em Construção | Estrutura definida; detalhes móveis. |
| `[🟠 IDEIA]` | Ideia / Hipótese | Proposta sem valor de verdade. |
| `[🔴 DESCONHECIDO]` | Desconhecido | Lacuna; **PROIBIDO inventar** para preencher. |

---

## 1. NÓS NARRATIVOS CENTRAIS (HUBS)

### [NÓ A] O REI MAGO / ALRIC — Antagonista Trágico (`NPC-000`)
- **John** — *Oposto filosófico: Força para Proteger vs Força para Exigir Reparação; colisão de destinos.* `[🟢 CANÔNICO]`
- **Antigo Rei de Arkan** — *Antigo servo/conselheiro traído; usurpação das criações de Alric.* `[🟢 CANÔNICO]`
- **Esposa de Alric** — *Cúmplice de vida no mundo paralelo; sobrevivente do cativeiro.* `[🟢 CANÔNICO]`
- **Filho de Alric (falecido)** — *Criança morta no cativeiro das Minas; motivo nuclear de ruptura.* `[🟢 CANÔNICO]`
- **Minas da Montanha (`LOCAL-007`)** — *Local do cativeiro e da morte do filho.* `[🟢 CANÔNICO]`
- **Reino do Rei Mago** — *Domínio soberano fundado no exílio.* `[🟢 CANÔNICO]`
- **Guerra da Reparação** — *Idealizador e comandante supremo.* `[🟢 CANÔNICO]`
- **LORE-001 / LORE-004 / LORE-005 / LORE-006** — *Origem, paralelo narrativo, prólogo e perfil público.* `[🟢 CANÔNICO]`
- **CANON-003** — *Decisão canônica da guerra e origem do conflito.* `[🟢 CANÔNICO]`
- **DOS-003** — *Dossiê investigativo confidencial (Fases 1 e 2 de Alric).* `[🟢 CANÔNICO]`

### [NÓ B] JOHN — Protagonista (`CANON-001`)
- **Vila de Arkham** — *Habitante e único soldado ativo.* `[🟢 CANÔNICO]`
- **Casa de John (`LOCAL-001`)** — *Ponto de spawn e início da jornada.* `[🟢 CANÔNICO]`
- **Diário de John (`ITEM-004` / `GAME-005` / `LORE-003`)** — *Memória da jornada; caderno indescartável.* `[🟢 CANÔNICO]`
- **Ancião Eldrin (`NPC-002`)** — *Mestre espiritual; fornecedor da Madeira Sagrada.* `[🟢 CANÔNICO]`
- **Mestre Cedric (`NPC-001`)** — *Ferreiro mentor; forjador da primeira lâmina.* `[🟢 CANÔNICO]`
- **Espada de Madeira Sagrada (`ITEM-003`)** — *Primeira arma canônica empunhada.* `[🟢 CANÔNICO]`
- **Rei Mago (`NPC-000`)** — *Oposto filosófico (Proteger vs Reparação).* `[🟢 CANÔNICO]`
- **Multiverso** — *Vítima de banimento forçado e futuro desbravador dimensional.* `[🟢 CANÔNICO]`

### [NÓ C] A JORNADA INICIAL (DIÁRIO → LIVRO → MULTIVERSO)
- **CANON-002** — *Início na Casa de John (coleta → bênção → forja).* `[🟢 CANÔNICO]`
- **CANON-006 / CANON-007** — *Diário elemento narrativo + protocolo narrativo Diário↔Livro.* `[🟢 CANÔNICO]`
- **LORE-002 / LORE-003 / LORE-005** — *Saga de John, registros do Diário e Prólogo literário.* `[🟢 CANÔNICO]`
- **LOCAL-008 + CANON-004** — *Portal do Mundo Livre; desacoplamento do Sandbox.* `[🟢 CANÔNICO]`
- **Livre / Multiverso (Capítulo 4)** — *🟡 EM CONSTRUÇÃO.* `[🟡 EM CONSTRUÇÃO]`

---

## 2. NÓS DE PERSONAGENS (NPC)

| Nó | Nome | Conecta-se a |
| :--- | :--- | :--- |
| `NPC-000` | O Rei Mago (Alric) | `LORE-001` `LORE-004` `LORE-005` `LORE-006` `LOCAL-007` `CANON-003` `CANON-001` `DOS-003` |
| `NPC-001` | Mestre Cedric | `LOCAL-002` `ITEM-001` `ITEM-002` `ITEM-003` `GAME-001` `NPC-002` `NPC-013` `LORE-002` `LORE-003` `DOS-001` |
| `NPC-002` | Ancião Eldrin | `LOCAL-004` `ITEM-002` `ITEM-003` `LORE-002` `NPC-001` `DOS-002` |
| `NPC-003` | Guarda Rowan | `LOCAL-003` `LOCAL-007` `GAME-001` `GAME-004` |
| `NPC-004` | Guarda Aldous | `LOCAL-003` `GAME-001` `GAME-004` |
| `NPC-005` | Padeira Beatrice | `LOCAL-005` `LOCAL-003` `GAME-006` `GAME-004` |
| `NPC-006` | Pescador Lucan | `LOCAL-006` `GAME-001` `GAME-004` |
| `NPC-007` | Mercador Tobias | `LOCAL-003` `LOCAL-009` `GAME-006` `GAME-004` |
| `NPC-008` | Agricultor Hugo | `LOCAL-001` `NPC-012` `LOCAL-009` `GAME-006` |
| `NPC-009` | Guardião Seraphin | `LOCAL-008` `CANON-004` |
| `NPC-010` | Lenhador Garrick | `ITEM-001` `NPC-001` |
| `NPC-011` | Mineiro Borin | `LOCAL-007` `LORE-001` `DOS-003` |
| `NPC-012` | Agricultora Nalia | `LOCAL-003` `NPC-008` `LOCAL-009` |
| `NPC-013` | Fazendeiro Geraldo | `LOCAL-009` `GAME-006` `NPC-008` `NPC-012` |

---

## 3. NÓS DE LOCAIS (LOCAL)

| Nó | Nome | Conecta-se a |
| :--- | :--- | :--- |
| `LOCAL-001` | Casa de John | `LORE-002` `LORE-003` `NPC-008` `ITEM-001` `ITEM-004` `CANON-002` |
| `LOCAL-002` | Oficina do Cedric | `NPC-001` `ITEM-003` `GAME-001` `LORE-002` |
| `LOCAL-003` | Praça Central de Arkham | `NPC-004` `NPC-005` `NPC-007` `NPC-012` `LOCAL-005` `LOCAL-009` `GAME-006` |
| `LOCAL-004` | Árvore Sagrada & Santuário | `NPC-002` `ITEM-002` `DOS-002` |
| `LOCAL-005` | Padaria da Vila | `NPC-005` `LOCAL-003` `GAME-006` |
| `LOCAL-006` | Cais do Lago Nobre | `NPC-006` `GAME-001` |
| `LOCAL-007` | Minas da Montanha Leste | `NPC-000` `NPC-003` `NPC-011` `LORE-001` `LORE-006` `DOS-003` |
| `LOCAL-008` | Portal do Mundo Livre | `NPC-009` `CANON-004` |
| `LOCAL-009` | Fazenda de Arkan | `CANON-008` `GAME-006` `LOCAL-003` `LOCAL-005` `NPC-005` `NPC-007` `NPC-008` `NPC-013` |

---

## 4. NÓS DE ITENS & EQUIPAMENTOS (ITEM)

| Nó | Nome | Conecta-se a |
| :--- | :--- | :--- |
| `ITEM-001` | Madeira Comum | `LOCAL-001` `NPC-001` `ITEM-003` `NPC-008` `NPC-010` |
| `ITEM-002` | Madeira Sagrada | `LOCAL-004` `NPC-002` `ITEM-003` |
| `ITEM-003` | Espada de Madeira Sagrada | `ITEM-001` `ITEM-002` `NPC-001` `NPC-002` `GAME-002` `LORE-002` |
| `ITEM-004` | Diário de John | `CANON-006` `CANON-007` `GAME-005` `LORE-003` `LOCAL-001` |

---

## 5. NÓS DE LORE & NARRATIVA (LORE)

| Nó | Nome | Conecta-se a |
| :--- | :--- | :--- |
| `LORE-001` | Origem do Conflito de Arkan e o Rei Mago | `LORE-004` `LORE-005` `LORE-006` `LOCAL-007` `CANON-003` `NPC-000` `DOS-003` |
| `LORE-002` | A Jornada e Evolução de John | `LORE-001` `LORE-003` `LORE-004` `NPC-001` `NPC-002` `ITEM-001` `ITEM-002` `ITEM-003` `CANON-001` `GAME-001` |
| `LORE-003` | Diário de John — Registros da Jornada | `CANON-006` `CANON-007` `GAME-005` `LORE-001` `LORE-002` `LORE-004` `LOCAL-001` `NPC-001` `NPC-002` `ITEM-004` |
| `LORE-004` | Paralelo Narrativo: John e o Rei Mago | `LORE-001` `LORE-002` `CANON-003` `NPC-000` `CANON-001` |
| `LORE-005` | Prólogo: Antes das Batalhas | `LORE-001` `LORE-002` `LORE-003` `LORE-004` `LOCAL-001` `LOCAL-007` `CANON-003` `CANON-007` |
| `LORE-006` | Perfil Público: O Rei Mago (Alric) | `LORE-001` `LORE-004` `LORE-005` `NPC-000` `LOCAL-007` `DOS-003` `CANON-003` |

---

## 6. NÓS DE GAMEPLAY & SISTEMAS (GAME)

| Nó | Nome | Conecta-se a |
| :--- | :--- | :--- |
| `GAME-001` | Loop Principal e Progressão | `LORE-002` `NPC-001` `NPC-002` `ITEM-003` `CANON-002` |
| `GAME-002` | Sistema de Combate e Combos | `ITEM-003` `GAME-001` `CANON-005` |
| `GAME-003` | Locomoção, Dash e Pulo | `GAME-002` `GAME-004` `CANON-005` |
| `GAME-004` | Sistema de Diálogo e Câmera | `NPC-001` `NPC-002` `GAME-001` `GAME-003` `CANON-005` |
| `GAME-005` | Sistema do Diário de John | `CANON-006` `CANON-007` `LORE-003` `LOCAL-001` `GAME-001` `ITEM-004` |
| `GAME-006` | Cadeia Produtiva e Economia Rural | `LOCAL-009` `CANON-008` `LOCAL-003` `LOCAL-005` `NPC-005` `NPC-007` `NPC-008` `NPC-012` `NPC-013` |

---

## 7. NÓS DE CÂNONE (CANON / BP-2026)

| Nó | Nome | Conecta-se a |
| :--- | :--- | :--- |
| `CANON-001` | Protagonista John e Origem do Soldado | `NPC-000` `LORE-002` `LORE-004` `CANON-002` |
| `CANON-002` | Início da Jornada na Casa de John | `LOCAL-001` `LORE-002` `ITEM-001` `CANON-001` |
| `CANON-003` | A Guerra contra o Rei Mago | `NPC-000` `LORE-001` `LORE-006` `LOCAL-007` |
| `CANON-004` | Desacoplamento do Sandbox | `LOCAL-008` `NPC-009` |
| `CANON-005` | Padrão de UX Multiplataforma | `GAME-001` `GAME-002` `GAME-003` `GAME-004` |
| `CANON-006` | Diário de John — Elemento Narrativo e Funcional | `LORE-002` `LORE-003` `CANON-001` `CANON-002` `LOCAL-001` `ITEM-004` |
| `CANON-007` | Protocolo Narrativo Diário↔Livro | `CANON-006` `LORE-002` `LORE-003` `GAME-005` `CANON-001` |
| `CANON-008` | Expansão Rural e Masterplan da Fazenda | `LOCAL-009` `GAME-006` `LOCAL-003` `LOCAL-005` `CANON-004` |

---

## 8. NÓS DE DOSSIÊS (DOS)

| Nó | Nome | Entidade Ref. | Conecta-se a |
| :--- | :--- | :--- | :--- |
| `DOS-001` | Mestre Cedric — Dossiê Completo | `NPC-001` | `LOCAL-002` `ITEM-003` `DOS-002` `DOS-003` |
| `DOS-002` | Árvore Sagrada — Dossiê de Mistério | `LOCAL-004` | `NPC-002` `ITEM-002` `DOS-001` `DOS-003` |
| `DOS-003` | O Rei Mago — Dossiê Investigativo | `NPC-000` | `LOCAL-007` `LORE-001` `LORE-006` `DOS-001` `DOS-002` |

---

## 9. MATRIZ DE IMPACTO DE MUDANÇAS (REGRA DO BIBLIOTECÁRIO)

Se você alterar:
1. **O destino da família do mago:** Revisar obrigatoriamente `LORE-001`, `LORE-005`, `LORE-006`, diálogos do `NPC-011 (Borin)`, narrativa de `LOCAL-007 (Minas)` e `DOS-003`.
2. **A origem/identidade de John:** Revisar `CANON-001`, `CANON-002`, `LORE-002`, `LORE-003 (Diário)`, `LORE-004` e a ficha de `LOCAL-001 (Casa de John)`.
3. **A natureza da Madeira Sagrada:** Revisar `ITEM-002`, `ITEM-003`, `NPC-002 (Eldrin)`, `LOCAL-004` e `GAME-001/GAME-002`.
4. **A rota de coleta da Madeira Comum:** Revisar `ITEM-001`, `NPC-008 (Hugo)`, `NPC-010 (Garrick)` e `LOCAL-001`.
5. **A estrutura econômica rural:** Revisar `LOCAL-009`, `GAME-006`, `CANON-008`, `NPC-013 (Geraldo)`, `NPC-005`, `NPC-007` e `NPC-012`.
6. **A conexão Multiverso / Sandbox:** Revisar `LOCAL-008`, `NPC-009 (Seraphin)`, `CANON-004` e o Capítulo 4 do Livro.
7. **A mecânica do Diário:** Revisar `ITEM-004`, `GAME-005`, `LORE-003`, `CANON-006` e `CANON-007`.
8. **A personalidade/roteiro de um NPC de vila:** Revisar também o nó do NPC no grafo acima + `GAME-004` (diálogos) + o Dossiê correspondente (se houver).

---

## 10. NOTAS OPERACIONAIS DO BIBLIOTECÁRIO

- **Sincronização obrigatória:** frontmatter `relacionados:` de cada ficha `/gdd/` ↔ este grafo ↔ `index.html` (Códice v2.8.0 lê ao vivo).
- **IDs referenciais:** usar sempre o padrão do AGENTS.md (`NPC-XXX`, `LOCAL-XXX`, `ITEM-XXX`, `GAME-XXX`, `CANON-XXX`/`BP-2026-XXX`, `LORE-XXX`, `DOS-XXX`).
- **Pontos cegos conhecidos** (não inventar conexões): Serraria (NPC-010 Garrick) não possui ficha `LOCAL` própria ainda; o destino exato da família de Alric e a origem de seus poderes permanecem `[🔴 DESCONHECIDO]`.