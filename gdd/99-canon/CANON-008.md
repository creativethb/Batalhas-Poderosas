---
id: "BP-2026-008"
nome: "Expansão Rural e Masterplan da Fazenda de Arkan"
status: "CANONICO"
relacionados:
  - "LOCAL-009"
  - "GAME-006"
  - "LOCAL-003"
  - "LOCAL-005"
  - "BP-2026-004"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "2026-09-11"
---

# Decisão Canônica: Expansão Rural e Masterplan da Fazenda de Arkan

```text
STATUS: CANÔNICO / CONCLUÍDO
DECISÃO: A Fazenda de Arkan é a área oficial de expansão agropecuária e econômica da Vila de Arkham.
1. CONCENTRAÇÃO RURAL: As atividades rurais dispersas no interior da vila são migradas para a Fazenda de Arkan,
   estabelecida em terreno externo delimitado (768.000 studs²).
2. PRESERVAÇÃO DO MASTERPLAN: Todos os 26 lotes, 5 setores, corredores e Nodes catalogados no Blueprint
   oficial (136 elementos) e no FazendaManager (32 zonas) são imutáveis em sua geometria e zoneamento.
3. PROTOCOLO DE DEMARCAÇÃO: As peças físicas de demarcação são temporárias e removidas após a validação
   das construções definitivas, enquanto as referências lógicas no código e ReplicatedStorage permanecem.
4. ESTADO DE CATALOGAÇÃO: A construção da Fazenda nesta etapa está CONCLUÍDA — 26/26 estruturas e áreas
   catalogadas como construídas. Nenhuma das 26 áreas permanece como PLANEJADO, PENDENTE ou EM CONSTRUÇÃO.
   O Blueprint (136 elementos) e o FazendaManager (32 zonas) permanecem apenas como referência TÉCNICA.
DATA: 11/09/2026
```

---

## 1. Motivação e Contexto

Com o crescimento da Vila de Arkham e o objetivo de aprofundar os sistemas de gameplay imersivo, cadeia produtiva e economia, tornou-se necessária a criação de um distrito rural autônomo e de grande escala fora dos limites urbanos da vila.

A Fazenda de Arkan concentra:
- Cultivo extensivo (Milho, Trigo, Vegetais, Cultivos Variados, Pomar, Horta);
- Criação e manejo zootécnico (Estábulo, Curral Principal, Galinheiro, Ovelhas, Porcos);
- Cadeia de transformação e estocagem (Moinho, Beneficiamento, Celeiro, Armazém, Depósito de Feno);
- Administração e apoio (Casa do Fazendeiro, Galpão de Ferramentas, Poço, Reservatório, Pátio de Carga e Área de Carroças).

---

## 2. Regras de Ouro do Masterplan

1. **Intocabilidade Espacial:** Nenhuma nova construção ou script pode reposicionar corredores, estradas ou alterar dimensões de lotes estabelecidos.
2. **Ciclo de Vida da Demarcação:**
   $$\text{Demarcação Física} \longrightarrow \text{Construção Definitiva} \longrightarrow \text{Validação} \longrightarrow \text{Remoção da Demarcação Física}$$
3. **Persistência Técnica:** O `Fazenda_Arkan_Blueprint` (em `ReplicatedStorage`) e o script `FazendaManager` (em `ServerScriptService`) são elementos lógicos permanentes e **NÃO** devem ser deletados ou limpos durante limpezas de cenário.

---

## 3. Construções da Fazenda — Concluídas (26/26)

Todas as 26 estruturas e áreas abaixo estão catalogadas como **concluídas**. Nenhuma permanece pendente, planejada ou em construção nesta etapa:

| Nº | Estrutura / Área |
| :--- | :--- |
| 1 | Casa do Fazendeiro |
| 2 | Armazém de Produção |
| 3 | Celeiro Principal |
| 4 | Estábulo Rural |
| 5 | Galpão de Ferramentas |
| 6 | Beneficiamento |
| 7 | Depósito de Feno |
| 8 | Moinho |
| 9 | Curral Principal |
| 10 | Galinheiro |
| 11 | Cercado de Ovelhas |
| 12 | Cercado de Porcos |
| 13 | Campo de Milho / Milharal |
| 14 | Campo de Trigo |
| 15 | Campo de Vegetais |
| 16 | Campo Variado |
| 17 | Pomar |
| 18 | Horta |
| 19 | Poço |
| 20 | Reservatório |
| 21 | Área de Carroças |
| 22 | Pátio Econômico |
| 23 | Pasto de Animais Futuros |
| 24 | Expansão Agrícola |
| 25 | Expansão Estrutural |
| 26 | Pátio de Carga |

### Classificação de Status das Estruturas

| Categoria | Estruturas Abrangidas | Status no GDD |
| :--- | :--- | :--- |
| **Construído / Confirmado** | Todas as 26 estruturas e áreas (Casa do Fazendeiro, Armazém de Produção, Celeiro Principal, Estábulo Rural, Galpão de Ferramentas, Beneficiamento, Depósito de Feno, Moinho, Curral Principal, Galinheiro, Cercado de Ovelhas, Cercado de Porcos, Campo de Milho, Campo de Trigo, Campo de Vegetais, Campo Variado, Pomar, Horta, Poço, Reservatório, Área de Carroças, Pátio Econômico, Pasto de Animais Futuros, Expansão Agrícola, Expansão Estrutural e Pátio de Carga). | `CANONICO` (Concluído) |
| **Referência Técnica** | Blueprint `Fazenda_Arkan_Blueprint` (136 elementos) e `ServerScriptService.FazendaManager` (32 zonas) — referências lógicas do Masterplan, não construções do mundo. | `CANONICO` (Infraestrutura Lógica) |

> **Regra de Expansão Futura:** A construção da Fazenda nesta etapa está concluída. Não criar nova fila de construções automaticamente. Novas construções serão tratadas como expansões futuras ou novas necessidades de gameplay, caso sejam definidas posteriormente.
