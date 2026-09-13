---
id: "LOCAL-009"
nome: "Fazenda de Arkan"
tipo: "Expansão Rural, Agrícola & Econômica"
status: "CANONICO"
localizacao: "Perímetro Rural Externo (Norte/Noroeste de Arkham)"
relacionados:
  - "BP-2026-008"
  - "GAME-006"
  - "LOCAL-003"
  - "LOCAL-005"
  - "NPC-005"
  - "NPC-007"
  - "NPC-008"
  - "NPC-012"
  - "NPC-013"
imagem: "./assets/locais/LOCAL-001.png"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "2026-09-11"
---

# Ficha de Local: Fazenda de Arkan

## 1. Identidade & Função
A **Fazenda de Arkan** é a principal área rural, produtiva e econômica associada à Vila de Arkham. Localizada fora do perímetro urbano principal de Arkham (além da barreira existente da vila), é o polo agropecuário oficial do reino, substituindo gradativamente as pequenas plantações dispersas no interior da vila.

A Fazenda opera como **cenário de gameplay ativo e econômico** — não como mero cenário decorativo. Sua função inclui:

- **Agricultura:** milho, trigo, vegetais, cultivos variados, pomar e horta;
- **Criação e manejo de animais:** estábulo, curral, galinheiro, ovelhas e porcos;
- **Armazenamento:** celeiro, armazém de produção e depósito de feno;
- **Beneficiamento e processamento:** linha de beneficiamento e moinho;
- **Transporte e logística:** pátio de carga e área de carroças;
- **Economia:** pátio econômico e cadeia produtiva integrada à Vila de Arkham;
- **Futura integração com NPCs, missões e expansão territorial de Arkham.**

---

## 2. Estado Oficial Atual

> **STATUS: CANÔNICO / CONCLUÍDO — 26/26 construções e áreas catalogadas como construídas.**
>
> A etapa atual de construção da Fazenda de Arkan está **concluída**. Nenhuma das 26 áreas permanece como "planejada", "pendente" ou "em construção". Novas construções posteriores serão tratadas como expansões futuras ou novas necessidades de gameplay.

---

## 3. Masterplan Oficial & Dimensões

| Parâmetro | Valor Canônico |
| :--- | :--- |
| **Área Geral** | 960 × 800 studs |
| **Área Total** | 768.000 studs² |
| **Centro da Fazenda** | `X = -10, Y = 124.2, Z = -1110` |
| **Limites em X** | `X_min = -490` até `X_max = 470` |
| **Limites em Z** | `Z_min = -1510` até `Z_max = -710` |
| **Entrada Principal** | `(-10, 124.2, -650)` |
| **Corredor Principal de Entrada** | 60 studs |
| **Organização Espacial** | 26 lotes e setores do Masterplan |

O Masterplan deve ser preservado integralmente. Nenhuma construção tem autorização para alterar a posição dos lotes, estradas, corredores ou Nodes oficiais.

---

## 4. Orientação Espacial e Corredores

- **Norte:** `-Z`
- **Sul:** `+Z`
- **Leste:** `+X`
- **Oeste:** `-X`

### Eixos Principais
- **Estrada de Entrada:** relativa aproximadamente `Z = +400.25`
- **Eixo Principal Norte/Sul:** relativa aproximadamente `Z = -29.75` (Largura: 32 studs)

### Corredores de Setores (Dimensões ~960 × 20 studs cada)
- **Corredor do Setor A:** `Z ≈ 290.25`
- **Corredor do Setor B:** `Z ≈ 80.25`
- **Corredor do Setor C:** `Z ≈ -129.75`
- **Corredor do Setor D:** `Z ≈ -339.75`

---

## 5. Sistema de Referência e Zonas Técnicas

### Blueprint Canônico (Referência Lógica — não é construção do mundo)
- **Caminho:** `ReplicatedStorage.Fazenda_Arkan_Blueprint`
- **Elementos Catalogados:** 136 elementos
- **Origem Registrada:** `X ≈ -11.5, Y ≈ 127.95, Z ≈ -1083.46`
- **Conteúdo:** Nodes, Lotes, Blocos de Escala, Cercas, Placas, Estradas e Corredores de demarcação.

### Gerenciador de Zonas (Controlador)
- **Caminho:** `ServerScriptService.FazendaManager`
- **Zonas Indexadas:** 32 zonas funcionais indexadas (Node, Lote, BlocoEscala, Cerca, Placa).

### Regra das Demarcações
As peças físicas de **Node, Lote, BlocoEscala, Cerca e Placa** foram utilizadas como referências temporárias de construção e são substituídas visualmente pelas construções definitivas. Entretanto, o `Fazenda_Arkan_Blueprint` e o `FazendaManager` **permanecem permanentemente** como referências lógicas e técnicas do Masterplan — e **não** são registrados como construções do mundo.

---

## 6. Construções e Áreas Concluídas (26/26)

| Nº | Estrutura / Área | Categoria | Dimensões / Lote | Funções & Características |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Casa do Fazendeiro** | Administração / Residência | Lote: `160 × 90 studs` | Residência principal, administração, escritório, convivência, cozinha e quartos. |
| 2 | **Armazém de Produção** | Armazenamento / Logística | Escala: `100 × 60 × 35 studs`<br>Lote: `160 × 90 studs` | Recebimento, estocagem, triagem agrícola e preparação logística. Node rel: `(-96.00, 4.89, 235.25)`, Centro abs: `(-107.50, 132.84, -848.21)`. |
| 3 | **Celeiro Principal** | Armazenamento | Escala: `100 × 60 × 50 studs`<br>Lote: `180 × 90 studs` | Grande estrutura de feno, palha, grãos, equipamentos rurais e circulação de operários. |
| 4 | **Estábulo Rural** | Animais / Locomoção | Estrutura de Manejo | Baias, alimentação, abrigo de animais de tração e suporte a carroças. |
| 5 | **Galpão de Ferramentas** | Infraestrutura | Lote: `180 × 90 studs` | Manutenção, guarda de implementos agrícolas e suporte aos trabalhadores rurais. |
| 6 | **Beneficiamento** | Processamento | Lote: `160 × 90 studs` | Triagem, processamento, separação de grãos/hortaliças e transição logística. |
| 7 | **Depósito de Feno** | Armazenamento | Lote: `200 × 90 studs` | Armazenamento especializado de forragem, feno e palha para nutrição animal. |
| 8 | **Moinho** | Processamento | Estrutura Mecânica | Moagem de cereais/trigo, engrenagens e conexão com a padaria e armazéns. |
| 9 | **Curral Principal** | Animais / Manejo | Área de Manejo | Contenção, manejo de gado/animais de médio porte e portões de triagem. |
| 10 | **Galinheiro** | Animais (Avícola) | Estrutura Avícola | Criação de aves, abrigo fechado, cercado externo e coleta de ovos. |
| 11 | **Cercado de Ovelhas** | Animais / Pastoreio | Área de Pastoreio | Pasto cercado, abrigo, tosquia e produção de lã para tecelagem. |
| 12 | **Cercado de Porcos** | Animais / Suinocultura | Área de Manejo | Criação e manejo suíno, alimentação e estrutura de contenção. |
| 13 | **Campo de Milho / Milharal** | Área Agrícola | Área Agrícola | Fileiras ordenadas de milho, suporte a colheita e integração econômica. |
| 14 | **Campo de Trigo** | Área Agrícola | Área Agrícola | Canteiros e fileiras de trigo dourado para abastecimento do Moinho e Padaria. |
| 15 | **Campo de Vegetais** | Área Agrícola | Área Agrícola | Canteiros de cenouras, cebolas, repolhos, beterrabas e abóboras. |
| 16 | **Campo Variado** | Área Agrícola | Área Agrícola | Cultivo misto de cevada, aveia, ervas e leguminosas complementares. |
| 17 | **Pomar** | Área Agrícola (Frutíferas) | Área Agrícola | Cultivo de árvores frutíferas e pomicultura organizada. |
| 18 | **Horta** | Área Agrícola (Hortaliças) | Área Agrícola | Hortaliças finas e cultivo intensivo de hortaliças. |
| 19 | **Poço** | Infraestrutura Hidráulica | Estrutura Hídrica | Captação de água para consumo, irrigação e apoio às áreas agrícolas. |
| 20 | **Reservatório** | Infraestrutura Hidráulica | Estrutura Hídrica | Reserva de água para irrigação e abastecimento. |
| 21 | **Área de Carroças** | Logística / Transporte | Área Logística | Estacionamento, manutenção e movimentação de carroças. |
| 22 | **Pátio Econômico** | Economia / Comércio | Área Comercial | Espaço de feiras, trocas e integração econômica da Fazenda. |
| 23 | **Pasto de Animais Futuros** | Pecuária / Expansão | Área de Pastagem | Pastagem preparada para futuros rebanhos e expansão pecuária. |
| 24 | **Expansão Agrícola** | Expansão Territorial | Área de Expansão | Área reservada para crescimento dos cultivos da Fazenda. |
| 25 | **Expansão Estrutural** | Expansão Territorial | Área de Expansão | Área reservada para novas estruturas e ampliação edificada. |
| 26 | **Pátio de Carga** | Logística / Transporte | Lote: `160 × 70 studs`<br>Bloco de escala: `100 × 2 × 40 studs` | Estacionamento de carroças, carga e descarga de sacarias, transferência direta para o Armazém de Produção. Node rel: `(-96.00, 4.89, 335.25)`. |

---

## 7. Relações Logísticas e Técnicas Importantes

- **Armazém de Produção ↔ Pátio de Carga:** Relação intencional de carga/descarga direta. O Pátio de Carga (`Node_Fazenda_PatioCarga`) ocupa a posição relativa `(-96.00, 4.89, 335.25)` (direção `+Z` imediata ao Armazém, cujo Node relativo é `(-96.00, 4.89, 235.25)`).
- **Escala oficial do Armazém de Produção:** `100 × 60 × 35 studs` em lote `160 × 90 studs`.
- **Escala oficial do Celeiro Principal:** `100 × 60 × 50 studs`.
- **Escala oficial do Pátio de Carga:** lote `160 × 70 studs` com bloco de escala `100 × 2 × 40 studs`.

---

## 8. Cadeia Econômica e de Produção

### Cadeia Agrícola
```
PLANTIO → CRESCIMENTO → COLHEITA → TRANSPORTE → ARMAZENAMENTO
→ BENEFICIAMENTO → PROCESSAMENTO → DISTRIBUIÇÃO → ECONOMIA DE ARKAN
```

### Cadeia de Criação Animal
```
ALIMENTAÇÃO → CRIAÇÃO → MANEJO → PRODUÇÃO → COLETA
→ ARMAZENAMENTO / COMÉRCIO
```

A lógica detalhada de integração, NPCs e destinos dos produtos está registrada em `GAME-006`.

---

## 9. Estado do Projeto & Próximas Frentes

- **Construção concluída nesta etapa:** 26/26 estruturas e áreas.
- **Sem fila de construções pendentes:** nenhuma área registrada como "planejada", "pendente" ou "em construção".
- **Expansões futuras:** novas construções posteriores serão tratadas como **expansões futuras** ou como novas necessidades de gameplay, caso sejam definidas posteriormente.
- **Próximas frentes de trabalho:** integração de gameplay (ProximityPrompts, ciclos de colheita), rotinas de NPCs agrícolas e missões associadas à Fazenda.

---

## 10. Princípios Construtivos & Integração
- Rigoroso alinhamento aos lotes, Nodes e blocos de escala oficiais.
- Proporção anatômica R15 em portas, corredores e alturas de tetos.
- Detalhamento inteligente com SurfaceAppearance e otimização por LoD para evitar gargalos de renderização e física no Roblox Studio.