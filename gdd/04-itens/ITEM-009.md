---
id: "ITEM-009"
nome: "Membrana de Vesplume"
funcao: "Material de espólio do Vesplume"
tipo: "Material"
raridade: "Comum"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1 / alforge de John"
relacionados:
  - "BEST-017"
  - "GAME-009"
  - "GAME-011"
imagem: "./assets/itens/ITEM-009.svg"
atualizado_por: "Codex"
data_atualizacao: "2026-10-08"
---

# Membrana de Vesplume

## Identificação e representação

ID documental **ITEM-009**; ID estável no inventário **membrana_vesplume**. Categoria: material; raridade: **Comum**. Natureza biológica, sem propriedade sagrada atribuída.

Miniatura vetorial estilizada implementada na inspeção, ficha independente e bolsa; arte documental em ./assets/itens/ITEM-009.svg. Não há drops físicos no chão.

Material empilhável e persistente; limite técnico atual de 1.000.000 unidades, preservando o limite do serviço. Não é balanceamento econômico.

## Descrição e propriedades

**Prévia:** Membrana leve e flexível das asas.

Fragmento de membrana das asas, leve e flexível. Nenhuma propriedade curativa ou receita está definida nesta etapa.

## Origem e obtenção

Vesplume derrotado no Piso 1 → corpo inspecionável → sorteio único compartilhado → seleção de quantidade → coleta → bolsa existente.

Chance provisória por entrada: **40%**, após passar pelo teste de vazio de 20%. Quantidade sorteada: **1–3**. Entradas independentes; nenhum material garantido. GAME-011 contém as regras completas.

## Uso atual

Coletar, guardar na bolsa e consultar informações. Não há consumo, venda, troca, receita, aprimoramento ou contrato implementado.

## Possibilidades futuras e destinos

Possíveis aplicações no boticário ou no artesanato.

Boticário ou artesão, como possibilidades futuras. Venda, tratamento, receitas e preços não implementados.

Quantidades de receitas, transformação e resultado permanecem **PLANEJADOS / A DEFINIR**. Nenhuma nova profissão ou serviço foi habilitado.

## Implementação, testes e validação

**IMPLEMENTADO e TESTADO em Play local de PC:** catálogo, coleta seletiva, armazenamento pelo InventarioService, miniatura e informações. Materiais entram no Export/Import existente e no mesmo perfil BP_DataStore_V1.

O teste não comprova salvar/recarregar entre servidores reais. Multiplayer com dois a seis clientes, toque físico e controle físico permanecem pendentes. A validação estética final pelo responsável é distinta dos testes técnicos.
