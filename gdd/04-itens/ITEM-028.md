---
id: "ITEM-028"
nome: "Bolsa de Moedas Antigas"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Recompensa monetária / recipiente"
raridade: "Comum"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
imagem: "./assets/itens/ITEM-028.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Bolsa de Moedas Antigas

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-028; **coleção:** Baú Verdadeiro.
- **Categoria:** Recompensa monetária / recipiente.
- **Raridade proposta:** Comum; não determina uma probabilidade de drop.
- **Nome no catálogo:** Bolsa de Moedas Antigas.
- **ID de runtime:** `bolsa_moedas_antigas`; GDD `ITEM-028`.
- **Aparência:** Pequena bolsa de couro gasto com cordão; moedas de cobre e prata visíveis. Uma moeda dourada na arte representa uma possibilidade futura, não ouro garantido.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Bolsa envelhecida que pode guardar moedas de antigas expedições.

**Descrição detalhada:** Pequena bolsa de couro gasto com cordão; moedas de cobre e prata visíveis. Uma moeda dourada na arte representa uma possibilidade futura, não ouro garantido. Encontrada entre pertences de antigos exploradores, sem identificar seus donos ou estabelecer nova moeda histórica.

## História, origem e limites narrativos

Encontrada entre pertences de antigos exploradores, sem identificar seus donos ou estabelecer nova moeda histórica.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Moedas exibidas para coleta seletiva e crédito direto na carteira, como representação de ITEM-028. Não há recipiente físico adicional. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Representação das moedas creditadas diretamente na carteira existente. O cadastro informativo existe, mas a bolsa física não é sorteada, recebida nem aberta: o mesmo dinheiro não é entregue duas vezes.

**Direção de design aprovada (uso disponível conforme acima):** Representar uma recompensa monetária que poderá conter cobre e prata, com possibilidade rara de ouro. Quantias, chance de ouro e forma de abertura ficam a definir. Não cria outra carteira ou moeda.

**Decisão de implementação:** crédito direto selecionado pelo jogador, sem segunda abertura, item de bolsa ou duplicação do conteúdo monetário. Refinamento da apresentação é futuro.

## Comercialização e relação com NPCs

Destino de venda não definido. Não conceder preço à bolsa além das moedas nem criar conversão dupla.

John e a carteira existente são as referências futuras. Nenhuma entrega à Tesouraria é exigida ou implementada para abrir a bolsa.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-028.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Recompensas do Baú Verdadeiro](CATALOGO-RECOMPENSAS-BAU-VERDADEIRO.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
