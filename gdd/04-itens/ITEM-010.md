---
id: "ITEM-010"
nome: "Glândula Luminosa"
funcao: "Material de espólio do Vesplume"
tipo: "Material"
raridade: "Raro"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1 / alforge de John"
relacionados:
  - "BEST-017"
  - "GAME-009"
  - "GAME-011"
imagem: "./assets/itens/ITEM-010.svg"
atualizado_por: "Codex"
data_atualizacao: "2026-10-08"
---

# Glândula Luminosa

## Identificação e representação

ID documental **ITEM-010**; ID estável no inventário **glandula_luminosa**. Categoria: material; raridade: **Raro**. Natureza biológica, sem propriedade sagrada atribuída.

Miniatura vetorial estilizada implementada na inspeção, ficha independente e bolsa; arte documental em ./assets/itens/ITEM-010.svg. Não há drops físicos no chão.

Material empilhável e persistente; limite técnico atual de 1.000.000 unidades, preservando o limite do serviço. Não é balanceamento econômico.

## Descrição e propriedades

**Prévia:** Órgão responsável pela secreção luminosa.

Glândula orgânica ligada à produção de secreção bioluminescente. Interesse potencial para a Guilda, sem ativação de contratos ou receitas.

## Origem e obtenção

Vesplume derrotado no Piso 1 → corpo inspecionável → sorteio único compartilhado → seleção de quantidade → coleta → bolsa existente.

Chance provisória por entrada: **8%**, após passar pelo teste de vazio de 20%. Quantidade sorteada: **1**. Entradas independentes; nenhum material garantido. GAME-011 contém as regras completas.

## Uso atual

Coletar, guardar na bolsa e consultar informações. Não há consumo, venda, troca, receita, aprimoramento ou contrato implementado.

## Possibilidades futuras e destinos

Possíveis receitas avançadas de iluminação/alquimia; interesse da Guilda.

Guilda como destino previsto. Compra, contratos e preços não definidos.

Quantidades de receitas, transformação e resultado permanecem **PLANEJADOS / A DEFINIR**. Nenhuma nova profissão ou serviço foi habilitado.

## Implementação, testes e validação

**IMPLEMENTADO e TESTADO em Play local de PC:** catálogo, coleta seletiva, armazenamento pelo InventarioService, miniatura e informações. Materiais entram no Export/Import existente e no mesmo perfil BP_DataStore_V1.

O teste não comprova salvar/recarregar entre servidores reais. Multiplayer com dois a seis clientes, toque físico e controle físico permanecem pendentes. A validação estética final pelo responsável é distinta dos testes técnicos.
