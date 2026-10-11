---
id: "ITEM-027"
nome: "Bandagem de Campo"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Consumível / primeiros socorros"
raridade: "Comum"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
imagem: "./assets/itens/ITEM-027.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Bandagem de Campo

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-027; **coleção:** Baú Verdadeiro.
- **Categoria:** Consumível / primeiros socorros.
- **Raridade proposta:** Comum; não determina uma probabilidade de drop.
- **Nome no catálogo:** Bandagem de Campo.
- **ID de runtime:** `bandagem_campo`; GDD `ITEM-027`.
- **Aparência:** Pequena embalagem de tecido creme ou marrom claro com rolos de faixas limpas. Sem símbolos médicos modernos, sangue ou frascos mágicos.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Faixas limpas de primeiros socorros, acondicionadas em tecido.

**Descrição detalhada:** Pequena embalagem de tecido creme ou marrom claro com rolos de faixas limpas. Sem símbolos médicos modernos, sangue ou frascos mágicos. Material prático de primeiros socorros associado à preparação de exploradores. Fabricante e expedição de origem não estão definidos.

## História, origem e limites narrativos

Material prático de primeiros socorros associado à preparação de exploradores. Fabricante e expedição de origem não estão definidos.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual do **Baú Verdadeiro do Piso 1**. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Coletável individual do Baú Verdadeiro, persistente no alforge. USAR consome uma unidade e restaura 15% da vida máxima, limitada ao máximo. Não remove veneno ou outros estados.

**Direção de design aprovada (uso disponível conforme acima):** Consumir para restaurar 15% da vida máxima, respeitando o limite de HP. Não cura venenos, infecções nem efeitos especiais. Nenhuma dessas ações está funcional nesta etapa.

**Refinamento futuro:** duração de animação de consumo e regras especiais em combate ainda não definidas; quantidade e obtenção provisórias estão em GAME-013.

## Comercialização e relação com NPCs

Possibilidade de venda não definida; preço e comprador permanecem a definir.

John poderá usar a bandagem. Não criar serviço do Boticário, receita ou entrega por NPC apenas para completar a ficha.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-027.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Recompensas do Baú Verdadeiro](CATALOGO-RECOMPENSAS-BAU-VERDADEIRO.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
