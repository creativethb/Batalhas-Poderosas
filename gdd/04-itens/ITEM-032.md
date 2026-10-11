---
id: "ITEM-032"
nome: "Frasco de Óleo para Lamparina"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Suprimento / utilitário de iluminação"
raridade: "Comum"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
  - "ITEM-006"
  - "ITEM-036"
imagem: "./assets/itens/ITEM-032.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Frasco de Óleo para Lamparina

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-032; **coleção:** Baú Verdadeiro.
- **Categoria:** Suprimento / utilitário de iluminação.
- **Raridade proposta:** Comum; não determina uma probabilidade de drop.
- **Nome no catálogo:** Frasco de Óleo para Lamparina.
- **ID de runtime:** `frasco_oleo_lamparina`; GDD `ITEM-032`.
- **Aparência:** Frasco pequeno vedado com rolha, óleo âmbar visível e acabamento simples. Sem luz própria, partículas ou brilho mágico.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Recipiente vedado de óleo destinado à iluminação de expedições.

**Descrição detalhada:** Frasco pequeno vedado com rolha, óleo âmbar visível e acabamento simples. Sem luz própria, partículas ou brilho mágico. Suprimento de exploração subterrânea. A ficha não define origem comercial, fabricante, fórmula do óleo ou expedição específica.

## História, origem e limites narrativos

Suprimento de exploração subterrânea. A ficha não define origem comercial, fabricante, fórmula do óleo ou expedição específica.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual do **Baú Verdadeiro do Piso 1**. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Coletável individual do Baú Verdadeiro, persistente no alforge e consultável. Sem botão de uso funcional ou integração com iluminação.

**Direção de design aprovada (uso disponível conforme acima):** Abastecer equipamentos de iluminação quando existir um sistema compatível. Consumo, capacidade e equipamentos receptores não foram implementados. Não abastece automaticamente o Cordão Luminoso.

**Dependências ainda abertas:** Capacidade, duração de iluminação, regras de abastecimento e relação com o Candelabro de Expedição a definir. Não confundir óleo com o Fluido Luminescente de ITEM-006.

## Comercialização e relação com NPCs

Possibilidade de venda, comprador e preço permanecem a definir.

John poderá transportar o suprimento. Não atribuir venda a Tobias nem refinamento ao Boticário sem nova definição.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-032.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Recompensas do Baú Verdadeiro](CATALOGO-RECOMPENSAS-BAU-VERDADEIRO.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
