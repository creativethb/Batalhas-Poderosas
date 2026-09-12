---
id: "GAME-006"
nome: "Cadeia Produtiva e Economia Rural da Fazenda"
status: "CANONICO"
relacionados:
  - "LOCAL-009"
  - "BP-2026-008"
  - "LOCAL-003"
  - "LOCAL-005"
  - "NPC-005"
  - "NPC-007"
  - "NPC-008"
  - "NPC-012"
  - "GAME-001"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "2026-09-11"
---

# Cadeia Produtiva & Economia Rural da Fazenda de Arkan

A Fazenda de Arkan opera como o coração econômico e agropecuário do reino, estruturada como uma cadeia produtiva dinâmica e integrada. **A construção da Fazenda nesta etapa está concluída (26/26 estruturas e áreas).** Este sistema descreve a lógica operacional e econômica aplicada sobre o conjunto construído.

---

## 1. Fluxo de Produção Agrícola

A produção vegetal segue uma esteira integrada de valor:

```
[PLANTIO]
   │
   ▼
[CRESCIMENTO]
   │
   ▼
[COLHEITA] (Trigo, Milho, Vegetais, Cultivos Variados, Pomar, Horta)
   │
   ▼
[TRANSPORTE] (Carroças / Corredores de Acesso)
   │
   ▼
[ARMAZENAMENTO] (Celeiro Principal / Armazém de Produção / Depósito de Feno)
   │
   ▼
[BENEFICIAMENTO] (Triagem, Limpeza, Ensacamento)
   │
   ▼
[PROCESSAMENTO] (Moinho para farinhas, grãos e rações)
   │
   ▼
[DISTRIBUIÇÃO] (Padaria LOCAL-005, Armazém Central LOCAL-003, Pátio Econômico)
   │
   ▼
[ECONOMIA DE ARKAN]
```

---

## 2. Fluxo de Pecuária e Manejo Animal

A criação animal opera de forma cíclica e autossustentável:

```
[ALIMENTAÇÃO & FORRAGEM] (Depósito de Feno / Pastagens)
   │
   ▼
[CRIAÇÃO & ABRIGO] (Estábulo, Curral Principal, Galinheiro, Cercado de Ovelhas, Cercado de Porcos)
   │
   ▼
[MANEJO ZOOTÉCNICO] (Cuidados, alimentação, tosquia)
   │
   ▼
[PRODUÇÃO & COLETA] (Ovos, Lã, Leite, Força de Tração / Carroças)
   │
   ▼
[ARMAZENAMENTO / COMÉRCIO] (Oficinas artesanais, alfaiataria, alimentação da vila)
```

---

## 3. Integração com a Vila de Arkham e NPCs

| Estrutura / Setor | NPC Responsável / Relacionado | Destino dos Produtos |
| :--- | :--- | :--- |
| **Campo de Trigo & Moinho** | Agricultores locais / Nalia (`NPC-012`) | Farinha para a Padaria da Beatrice (`NPC-005`, `LOCAL-005`) |
| **Armazém & Pátio de Carga** | Trabalhadores rurais / Hugo (`NPC-008`) | Abastecimento do Armazém do Mercador Tobias (`NPC-007`, `LOCAL-003`) |
| **Estábulo & Ferramentas** | Tratadores de animais / Mestre Cedric (`NPC-001`) | Manutenção de ferraduras, eixos de carroça e implementos de corte |
| **Cercado de Ovelhas** | Futuro Pastor de Arkan | Fornecimento de lã para mantos, estofados e vestimentas |
| **Galinheiro & Curral** | Trabalhadores da Fazenda | Alimentos frescos e laticínios para a comunidade |

---

## 4. Diretrizes Técnicas de Gameplay

1. **Interatividade e ProximityPrompts:** Preparação para nós de colheita e carregamento de sacarias com feedback visual e sonoro.
2. **Ciclos de Spawn / Regeneração:** Áreas de cultivo com tempos de maturação configuráveis via scripts no Roblox Studio.
3. **Escala e Ergonomia:** Todos os acessos entre lotes e corredores comportam montarias, carroças e personagens com rig R15 sem colisões espúrias.
