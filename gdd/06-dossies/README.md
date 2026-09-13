# 📁 Dossiês — Arquitetura e Convenções

## Estrutura de Pastas

```
06-dossies/
├── 01-personagens/        # Dossiês de personagens principais (CHAR-XXX)
├── 02-npcs/               # Dossiês de NPCs (NPC-XXX)
├── 03-locais/             # Dossiês de locais (LOCAL-XXX)
├── 04-itens-e-artefatos/  # Dossiês de itens/artefatos (ITEM-XXX)
├── 05-eventos-historicos/ # Dossiês de eventos (EVT-XXX)
├── 06-linhagens-povos-faccoes/ # Dossiês de facções/linhagens (FAC-XXX)
├── 07-misterios/          # Dossiês de mistérios (MST-XXX)
├── 08-universo-geral/     # Dossiês gerais do universo (UNV-XXX)
└── _TEMPLATE_DOSsie.md    # Template base
```

## Convenção de IDs

| Subcategoria | Prefixo | Exemplo |
| :--- | :--- | :--- |
| Personagens | `CHAR-` | `CHAR-001` (John) |
| NPCs | `NPC-` | `NPC-001` (Cedric) — **reutiliza ID do GDD** |
| Locais | `LOCAL-` | `LOCAL-001` — **reutiliza ID do GDD** |
| Itens/Artefatos | `ITEM-` | `ITEM-001` — **reutiliza ID do GDD** |
| Eventos Históricos | `EVT-` | `EVT-001` |
| Linhagens/Povos/Facções | `FAC-` | `FAC-001` |
| Mistérios | `MST-` | `MST-001` |
| Universo Geral | `UNV-` | `UNV-001` |

> **Regra:** Dossiês de entidades que já existem no GDD (NPCs, Locais, Itens) **usam o mesmo ID**. Dossiês novos (Eventos, Facções, Mistérios) usam seus próprios prefixos.

## Frontmatter Padrão (YAML) — FASE 1 + FASE 2

```yaml
---
# === IDENTIFICAÇÃO BÁSICA (FASE 1) ===
id: "DOSSIER-XXX"                    # ID único do dossiê
nome: "Título do Dossiê"             # Título legível
tipo: "Dossiê"                       # Fixo: "Dossiê"
categoria: "personagens"             # Pasta pai: personagens|npcs|locais|itens-e-artefatos|eventos-historicos|linhagens-povos-faccoes|misterios|universo-geral
subcategoria: "personagens"          # Subpasta: 01-personagens|02-npcs|03-locais|04-itens-e-artefatos|05-eventos-historicos|06-linhagens-povos-faccoes|07-misterios|08-universo-geral
status: "EM_CONSTRUCAO"              # CANONICO|EM_CONSTRUCAO|IDEIA|PLANEJADO|DESCONTINUADO
entidade_ref: "CHAR-001"             # ID da entidade no GDD (se aplicável)
imagem: "./assets/..."               # Caminho da imagem (opcional)
resumo: "Resumo 1-2 parágrafos"      # Resumo breve
tags: ["tag1", "tag2"]               # Tags livres
relacionados: ["DOSSIER-YYY"]        # Dossiês relacionados
versao: "1.0"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "YYYY-MM-DD"

# === FASE 2: CLASSIFICAÇÃO, MARCAÇÃO E RASTREABILIDADE ===
info_id: "INFO-XXX"                  # ID estável da informação principal (ex: INFO-CEDRIC-001)
entidade_principal: "CHAR-001"       # ID da entidade principal (CHAR, NPC, LOCAL, ITEM, FAC, EVT, MST, UNV)
tipo_informacao: "biografia"         # biografia | historia | personalidade | conhecimento | relacionamento | evento | misterio | tecnica | lore | gameplay | cronologia | outro
categoria_classificacao: "identidade" # identidade | historia | psicologia | habilidades | relacoes | eventos | locais | itens | livro | diario | gameplay | misterios | cronologia | referencias
status: "EM_CONSTRUCAO"              # CANONICO | EM_CONSTRUCAO | IDEIA | DESCONHECIDO | DESCONTINUADO
periodo: ""                          # Era/Período histórico (ex: "Era Antiga", "Era Presente", "Infância", "Juventude")
localizacao: ""                      # LOCAL-XXX ou descrição livre
personagens_envolvidos: []           # IDs: ["NPC-001", "CHAR-001", "NPC-002"]
tema: ""                             # Tema principal (ex: "forja ancestral", "guerra da reparação")
origem: "narrativa_direta"           # narrativa_direta | banco_narrativo | decisao_canonica | gameplay | inferido | outro
relevancia_narrativa: "alta"         # alta | media | baixa
relevancia_gameplay: "media"         # alta | media | baixa | nenhuma
aplicabilidade_livro: true           # Pode ser usado no Grande Livro de Arkan
aplicabilidade_diario: false         # Pode ser usado no Diário de John
relacao_misterio: ""                 # ID do mistério relacionado (ex: MST-001) ou descrição
observacoes: ""                      # Observações livres

# Rastreabilidade
origem_documento: ""                 # Documento de origem (ex: "Bloco 1 Cedric", "PERS-002-CEDRIC.md")
origem_entidade: ""                  # Entidade de origem (ex: "NPC-001")
origem_registro: ""                  # Registro específico (ex: "Bloco 1 - Seção 3")
decisao_canonica: ""                 # Decisão canônica relacionada (ex: "BP-2026-001")
atualizacoes: []                     # Histórico: [{"data": "YYYY-MM-DD", "autor": "...", "descricao": "..."}]

# Destino / Aplicabilidade
destino: []                          # Onde pode ser usado: ["GDD", "LIVRO", "DIARIO", "NPC", "GAMEPLAY", "MISSAO", "CRONOLOGIA", "MISTERIO"]

versao: "1.0"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "YYYY-MM-DD"
---
```

## Convenções de Conteúdo

1. **Markdown livre** — o corpo do dossiê é Markdown puro, sem limite de tamanho
2. **Seções sugeridas** — use as do template (`_TEMPLATE_DOSsie.md`), mas adapte conforme necessidade
3. **Profundidade ilimitada** — dossiês podem ser muito maiores que fichas do GDD
4. **Referências cruzadas** — use IDs estáveis (`NPC-001`, `LOCAL-002`, `DOSSIER-005`, `BP-2026-008`)
5. **Status de canonização** — mesmo vocabulário do GDD

## Carregamento pelo Códice

O sistema **já detecta automaticamente** pastas sob `/gdd/` que contenham `.md`:
- A pasta `06-dossies/` aparece no menu "Categorias Customizadas"
- Subpastas (01-personagens, 02-npcs, etc.) tornam-se rotas `#categoria/06-dossies/01-personagens`
- O Inspetor abre e renderiza o Markdown completo
- Busca global (Ctrl+K) indexa `nome`, `id`, `markdown`, `resumo`, `tags`

## Criação de Novo Dossiê

### Via Modal "Nova Categoria" (criar subpasta)
1. Abrir modal "📁 NOVA CATEGORIA"
2. Nome: "Personagens"
3. Pasta: `gdd/06-dossies/01-personagens`
4. Ícone: `👤`
4. Isso cria `gdd/06-dossies/01-personagens/README.md`

### Via Modal "Novo Documento" (criar dossiê)
1. Abrir modal "➕ NOVO DOCUMENTO (.MD)"
2. Pasta: `gdd/06-dossies/01-personagens`
3. Preencher frontmatter conforme padrão
4. Conteúdo Markdown livre

## Compatibilidade

- **Não quebra** nenhuma funcionalidade existente do Códice v2.8.0
- **Não altera** IDs atuais (NPC-000...013, LOCAL-001...009, ITEM-001...004)
- **Não migra** lore existente — apenas prepara a estrutura
- **Renderização** usa o mesmo motor do Códice (parseFrontmatter + safeMarkdown)

## Próximas Fases (Não Implementar Agora)

| Fase | Foco |
| :--- | :--- |
| **FASE 2** | ✅ Classificação, tags, rastreabilidade, status semântico — **IMPLEMENTADA** |
| **FASE 3** | Relações bidirecionais, grafo de conexões, cruzamento |
| **FASE 4** | Integração GDD ↔ Livro ↔ Diário ↔ Gameplay ↔ Missões |
| **FASE 5** | Migração da lore completa (Cedric, Alric, John, Eldrin, etc.) |
| **FASE 6** | Protocolo do Bibliotecário automatizado |

---

## FASE 2: CLASSIFICAÇÃO, MARCAÇÃO E RASTREABILIDADE — DOCUMENTAÇÃO

> **Status:** ✅ Implementada (commit `xxx`)

### 1. Padrão de ID de Informação (`info_id`)

**Formato:** `INFO-{ENTIDADE}-{NNN}`  
**Exemplos:** `INFO-CEDRIC-001`, `INFO-ALRIC-001`, `INFO-ARKAN-001`, `INFO-MST-001`

**Regras:**
- Prefixo `INFO-` fixo
- Entidade principal em maiúsculas (pode ser abreviada)
- Número sequencial de 3 dígitos por entidade
- Estável, legível, único, pesquisável
- Compatível com IDs de entidades existentes (`NPC-001`, `CHAR-001`, etc.)

### 2. Sistema de Classificação (Campos Obrigatórios no Frontmatter)

| Campo | Tipo | Valores Permitidos / Descrição |
| :--- | :--- | :--- |
| `info_id` | string | ID estável da informação (ex: `INFO-CEDRIC-001`) |
| `entidade_principal` | string | ID da entidade principal (CHAR, NPC, LOCAL, ITEM, FAC, EVT, MST, UNV) |
| `tipo_informacao` | enum | `biografia` \| `historia` \| `personalidade` \| `conhecimento` \| `relacionamento` \| `evento` \| `misterio` \| `tecnica` \| `lore` \| `gameplay` \| `cronologia` \| `outro` |
| `categoria_classificacao` | enum | `identidade` \| `historia` \| `psicologia` \| `habilidades` \| `relacoes` \| `eventos` \| `locais` \| `itens` \| `livro` \| `diario` \| `gameplay` \| `misterios` \| `cronologia` \| `referencias` |
| `status` | enum | `CANONICO` \| `EM_CONSTRUCAO` \| `IDEIA` \| `DESCONHECIDO` \| `DESCONTINUADO` |
| `periodo` | string | Era/Período (ex: "Era Antiga", "Infância", "Juventude", "Vida Adulta", "Era Presente") |
| `localizacao` | string | `LOCAL-XXX` ou descrição livre |
| `personagens_envolvidos` | array | IDs: `["NPC-001", "CHAR-001", "NPC-002"]` |
| `tema` | string | Tema principal livre (ex: "forja ancestral") |
| `origem` | enum | `narrativa_direta` \| `banco_narrativo` \| `decisao_canonica` \| `gameplay` \| `inferido` \| `outro` |
| `relevancia_narrativa` | enum | `alta` \| `media` \| `baixa` |
| `relevancia_gameplay` | enum | `alta` \| `media` \| `baixa` \| `nenhuma` |
| `aplicabilidade_livro` | boolean | Para uso no Grande Livro de Arkan |
| `aplicabilidade_diario` | boolean | Para uso no Diário de John |
| `relacao_misterio` | string | ID do mistério (ex: `MST-ALRIC-IDENTITY`) ou descrição |
| `observacoes` | string | Livre |

### 3. Status de Canonicidade (Preservado do Projeto)

| Status | Emoji | Significado |
| :--- | :--- | :--- |
| `CANONICO` | 🟢 | Oficial, aprovado, imutável sem ordem direta |
| `EM_CONSTRUCAO` | 🟡 | Em desenvolvimento ativo, estrutura definida, detalhes móveis |
| `IDEIA` | 🟠 | Hipótese/proposta, não pode ser tratada como verdade |
| `DESCONHECIDO` | 🔴 | Lacuna proposital — **PROIBIDO inventar para preencher** |
| `DESCONTINUADO` | ⚫ | Ideia rejeitada formalmente, mantida com justificativa |

> **Regra:** Não transformar automaticamente hipótese em cânone. Não apagar informação por causa do status.

### 4. Tags e Palavras-chave

**Campo:** `tags` (array de strings)

**Exemplo no DOSSIER-001-Cedric:**
```yaml
tags: ["ferreiro", "linhagem", "forja-ancestral", "arvore-sagrada", "alric", "tradição", "forja", "guerra-reparacao"]
```

**Busca/Filtros suportados:**
- "mostrar tudo com tag `alric`" → retorna Cedric, Eldrin, Alric, mistérios relacionados
- "mostrar tudo com tag `forja-ancestral`" → retorna Cedric, ferrarias, itens forjados
- "mostrar tudo `tipo_informacao: misterio`" → retorna todos os mistérios catalogados

### 5. Rastreabilidade (Campos de Origem)

| Campo | Descrição |
| :--- | :--- |
| `origem_documento` | Documento de origem (ex: `"banco_narrativo/01-personagens/PERS-002-CEDRIC.md"`) |
| `origem_entidade` | Entidade de origem (ex: `"NPC-001"`) |
| `origem_registro` | Registro específico (ex: `"Bloco 1 - Seção 3"`) |
| `decisao_canonica` | Decisão canônica relacionada (ex: `"BP-2026-001, BP-2026-002"`) |
| `atualizacoes` | Array de histórico: `[{"data": "2026-09-12", "autor": "agente_bibliotecario", "descricao": "..."}]` |

### 6. Destino / Aplicabilidade

**Campo:** `destino` (array)

**Valores permitidos:** `["GDD", "LIVRO", "DIARIO", "NPC", "GAMEPLAY", "MISSAO", "CRONOLOGIA", "MISTERIO"]`

### 6. Filtros e Consultas Disponíveis

O Códice suporta busca/filtro por (via busca global Ctrl+K + filtros no Inspetor):

| Critério | Campo do Frontmatter |
| :--- | :--- |
| ID do dossiê | `id` |
| ID da informação | `info_id` |
| Entidade principal | `entidade_principal` |
| Categoria | `categoria` / `subcategoria` |
| Status | `status` |
| Tag | `tags` |
| Palavra-chave livre | `markdown`, `resumo`, `tema` |
| Local | `localizacao` |
| Período | `periodo` |
| Tipo | `tipo_informacao` |
| Relevância | `relevancia_narrativa` / `relevancia_gameplay` |
| Origem | `origem` |
| Destino | `destino` |
| Rastreabilidade | `origem_documento`, `decisao_canonica` |

### 7. Testes Realizados

**Registros de Teste Criados (não contaminam lore canônica):**

| Arquivo | `info_id` | `entidade_principal` | `tipo_informacao` | `status` | Tags de teste |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `DOSSIER-001-CEDRIC.md` | `INFO-CEDRIC-001` | `NPC-001` | `biografia` | `EM_CONSTRUCAO` | `teste-fase2`, `ferreiro`, `alric` |

> **Nota:** O dossiê do Cedric foi atualizado com todos os campos da FASE 2 (versão 2.0). Não altera lore canônica — apenas adiciona metadados de classificação.