---
id: "ITEM-023"
nome: "Dente de Baú Falso"
funcao: "Material coletável por inspeção de Baú Falso"
tipo: "Material"
raridade: "Comum"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "BEST-022"
  - "GAME-009"
  - "GAME-011"
imagem: "./assets/itens/ITEM-023.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Dente de Baú Falso

> **IMPLEMENTADO / TESTADO EM PLAY LOCAL.** Integração autorizada em 11/10/2026. Identidade e balanceamento provisórios; não implica validação definitiva.

## Informações do item
- **ID documental:** ITEM-023. **ID de runtime:** `dente_bau_falso`.
- **Categoria:** material coletável; **raridade:** Comum; **origem:** Baú Falso (BEST-022).
- **Descrição curta para a interface:** Dente rígido da mandíbula.
- **Descrição detalhada:** Peça cortante; natureza orgânica ou artificial a validar.
- **Propriedades:** efeitos, bônus e natureza exata ainda não confirmados.

## Obtenção
Obtido pela inspeção do Baú Falso revelado e derrotado, usando GAME-011. Chance condicional provisória: **55%, 1–2 unidades**. Há 20% de vazio forçado; nos demais resultados as três entradas são independentes. Sem moedas, preço ou venda à Guilda nesta etapa.

## Utilidade
- **Uso atual:** coletar seletivamente, guardar no alforge e consultar informações.
- **Uso futuro possível:** Ferramentas e decoração. Nenhuma receita, vendedor, contrato, transformação ou efeito foi implementado.

## Imagem e integração
Imagem reservada: `./assets/itens/ITEM-023.png` (não criada). Miniatura nativa implementada em BP_ItemInterface, com metadados compartilhados entre inspeção, alforge e ficha independente; não apresentar funcionalidades planejadas como ativas. Preservar BancoDeItens, EspoliosConfig, EspoliosService, InventarioService, BP_ItemInterface e BP_DataStore_V1.

## Estado e validação
**IMPLEMENTADO / TESTADO localmente, sem VALIDADO.** Conferidos inspeção, miniatura, coleta parcial/integral, vazio, limites de quantidade e exportação do inventário. Multiplayer real, reconexão e balanceamento definitivo pendentes. Ver [catálogo consolidado](CATALOGO-ESPOLIOS-PROPOSTOS.md).
