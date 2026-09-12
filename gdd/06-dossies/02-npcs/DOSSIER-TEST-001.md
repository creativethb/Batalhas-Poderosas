---
id: "DOSSIER-TEST-001"
nome: "TESTE FASE 2 — Informação de Classificação"
tipo: "Dossiê"
categoria: "npcs"
subcategoria: "npcs"
status: "IDEIA"
entidade_ref: "NPC-001"
imagem: "./assets/npcs/NPC-001.jpg"
resumo: "Registro de teste para validar o sistema de classificação FASE 2. Não é lore canônica."
tags: ["teste-fase2", "ferreiro", "classificacao"]
relacionados: ["DOSSIER-001"]

# === FASE 2: CLASSIFICAÇÃO, MARCAÇÃO E RASTREABILIDADE ===
info_id: "INFO-TEST-001"
entidade_principal: "NPC-001"
tipo_informacao: "tecnica"
categoria_classificacao: "habilidades"
status: "IDEIA"
periodo: "Era Presente"
localizacao: "LOCAL-002"
personagens_envolvidos: ["NPC-001"]
tema: "teste de filtros"
origem: "outro"
relevancia_narrativa: "baixa"
relevancia_gameplay: "nenhuma"
aplicabilidade_livro: false
aplicabilidade_diario: false
relacao_misterio: ""
observacoes: "Registro sintético para validação do sistema FASE 2"

# Rastreabilidade
origem_documento: "teste_fase2_interno"
origem_entidade: "NPC-001"
origem_registro: "teste_fase2_001"
decisao_canonica: ""
atualizacoes: [{"data": "2026-09-12", "autor": "agente_bibliotecario", "descricao": "Criação registro de teste FASE 2"}]

# Destino / Aplicabilidade
destino: ["GDD"]

versao: "1.0"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "2026-09-12"
---

# TESTE FASE 2 — Informação de Classificação

> **Status:** 🟠 IDEIA | **Tipo:** técnica | **Categoria:** habilidades | **Entidade:** `NPC-001`

Este é um registro sintético criado exclusivamente para validar o sistema de classificação, marcação e rastreabilidade da FASE 2.

## Objetivo do Teste

Validar que o Códice consegue:
1. Carregar o campo `info_id` (`INFO-TEST-001`)
2. Aplicar filtros por `status` (IDEIA), `tipo_informacao` (tecnica), `categoria_classificacao` (habilidades)
3. Buscar por `tags` (teste-fase2, classificacao)
4. Filtrar por `entidade_principal` (NPC-001)
5. Exibir badge de status 🟠 IDEIA no card

## Metadados de Teste

| Campo | Valor |
| :--- | :--- |
| `info_id` | `INFO-TEST-001` |
| `entidade_principal` | `NPC-001` |
| `tipo_informacao` | `tecnica` |
| `categoria_classificacao` | `habilidades` |
| `status` | `IDEIA` |
| `periodo` | `Era Presente` |
| `localizacao` | `LOCAL-002` |
| `personagens_envolvidos` | `["NPC-001"]` |
| `tema` | `teste de filtros` |
| `origem` | `outro` |
| `relevancia_narrativa` | `baixa` |
| `relevancia_gameplay` | `nenhuma` |
| `aplicabilidade_livro` | `false` |
| `aplicabilidade_diario` | `false` |
| `tags` | `["teste-fase2", "ferreiro", "classificacao"]` |

## Rastreabilidade

- **Origem documento:** `teste_fase2_interno`
- **Origem entidade:** `NPC-001`
- **Decisão canônica:** (nenhuma)
- **Atualizações:** `[{"data": "2026-09-12", "autor": "agente_bibliotecario", "descricao": "Criação registro de teste FASE 2"}]`

## Destino

`["GDD"]`

---

> ⚠️ **ESTE REGISTRO É SINTÉTICO** — Não faz parte da lore canônica de Batalhas Poderosas. Existe apenas para validar o sistema FASE 2.