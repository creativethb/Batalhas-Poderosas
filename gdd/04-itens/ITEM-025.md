---
id: "ITEM-025"
nome: "Fechadura Viva"
funcao: "Material coletável por inspeção de Baú Falso"
tipo: "Material"
raridade: "Raro"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "BEST-022"
  - "GAME-009"
  - "GAME-011"
imagem: "./assets/itens/ITEM-025.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Fechadura Viva

> **IMPLEMENTADO / TESTADO EM PLAY LOCAL.** Integração autorizada em 11/10/2026. Identidade e balanceamento provisórios; não implica validação definitiva.

## Informações do item
- **ID documental:** ITEM-025. **ID de runtime:** `fechadura_viva`.
- **Categoria:** material coletável; **raridade:** Raro; **origem:** Baú Falso (BEST-022).
- **Descrição curta para a interface:** Mecanismo ligado ao disfarce.
- **Descrição detalhada:** Fechadura com movimento incomum; natureza não confirmada.
- **Propriedades:** efeitos, bônus e natureza exata ainda não confirmados.

## Obtenção
Obtido pela inspeção do Baú Falso revelado e derrotado, usando GAME-011. Chance condicional provisória: **8%, 1 unidade**. Há 20% de vazio forçado; nos demais resultados as três entradas são independentes. Sem moedas, preço ou venda à Guilda nesta etapa.

## Utilidade
- **Uso atual:** coletar seletivamente, guardar no alforge e consultar informações.
- **Uso futuro possível:** Pesquisa e mecanismos especiais. Nenhuma receita, vendedor, contrato, transformação ou efeito foi implementado.

## Imagem e integração
Imagem reservada: `./assets/itens/ITEM-025.png` (não criada). Miniatura nativa implementada em BP_ItemInterface, com metadados compartilhados entre inspeção, alforge e ficha independente; não apresentar funcionalidades planejadas como ativas. Preservar BancoDeItens, EspoliosConfig, EspoliosService, InventarioService, BP_ItemInterface e BP_DataStore_V1.

## Estado e validação
**IMPLEMENTADO / TESTADO localmente, sem VALIDADO.** Conferidos inspeção, miniatura, coleta parcial/integral, vazio, limites de quantidade e exportação do inventário. Multiplayer real, reconexão e balanceamento definitivo pendentes. Ver [catálogo consolidado](CATALOGO-ESPOLIOS-PROPOSTOS.md).
