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

## Frontmatter Padrão (YAML)

```yaml
---
id: "DOSSIER-XXX"              # ID único do dossiê
nome: "Título do Dossiê"       # Título legível
tipo: "Dossiê"                 # Fixo: "Dossiê"
categoria: "personagens"       # Pasta pai: personagens|npcs|locais|itens-e-artefatos|eventos-historicos|linhagens-povos-faccoes|misterios|universo-geral
subcategoria: "personagens"    # Subpasta: 01-personagens|02-npcs|03-locais|04-itens-e-artefatos|05-eventos-historicos|06-linhagens-povos-faccoes|07-misterios|08-universo-geral
status: "EM_CONSTRUCAO"        # CANONICO|EM_CONSTRUCAO|IDEIA|PLANEJADO|DESCONTINUADO
entidade_ref: "CHAR-001"       # ID da entidade no GDD (se aplicável)
resumo: "Resumo 1-2 parágrafos"
tags: ["tag1", "tag2"]         # Para classificação futura (FASE 2)
relacionados: ["DOSSIER-YYY"]  # Para relações futuras (FASE 3)
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
| **FASE 2** | Classificação, tags, rastreabilidade, status semântico |
| **FASE 3** | Relações bidirecionais, grafo de conexões, cruzamento |
| **FASE 4** | Integração GDD ↔ Livro ↔ Diário ↔ Gameplay ↔ Missões |
| **FASE 5** | Migração da lore completa (Cedric, Alric, John, Eldrin, etc.) |
| **FASE 6** | Protocolo do Bibliotecário automatizado |

---

> **Documento vivo** — atualize conforme a arquitetura evoluir.