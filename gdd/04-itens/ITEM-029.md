---
id: "ITEM-029"
nome: "Taça de Bronze Antiga"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Objeto comercial / antiguidade"
raridade: "Comum"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
imagem: "./assets/itens/ITEM-029.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Taça de Bronze Antiga

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-029; **coleção:** Baú Verdadeiro.
- **Categoria:** Objeto comercial / antiguidade.
- **Raridade proposta:** Comum; não determina uma probabilidade de drop.
- **Nome no catálogo:** Taça de Bronze Antiga.
- **ID de runtime:** `taca_bronze_antiga`; GDD `ITEM-029`.
- **Aparência:** Taça robusta de bronze, haste curta, base estável e decoração discreta. Pátina e marcas do tempo sem joias, brasões inéditos ou efeitos luminosos.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Taça de bronze marcada pelo tempo, com pequenos ornamentos.

**Descrição detalhada:** Taça robusta de bronze, haste curta, base estável e decoração discreta. Pátina e marcas do tempo sem joias, brasões inéditos ou efeitos luminosos. Pode ter servido a uso doméstico ou cerimonial. A finalidade original e a comunidade que a produziu não são fatos confirmados.

## História, origem e limites narrativos

Pode ter servido a uso doméstico ou cerimonial. A finalidade original e a comunidade que a produziu não são fatos confirmados.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual do **Baú Verdadeiro do Piso 1**. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Coletável individual do Baú Verdadeiro, persistente no alforge e consultável. A venda ainda não está habilitada.

**Direção de design aprovada (uso disponível conforme acima):** Objeto comercial destinado principalmente à futura venda na Guilda de Arkan. Seu interesse comercial deriva do material e da antiguidade; não possui poder especial conhecido.

**Dependências ainda abertas:** Valor provisório de compra, quantidade e probabilidade de obtenção a definir.

## Comercialização e relação com NPCs

Venda à Guilda proposta, ainda não implementada para este item. Preço, avaliação e aceitação no catálogo funcional não definidos.

Futura Atendente de Espólios e Contratos para avaliação e entrega; Tesouraria para o pagamento autorizado. Não criar novas atendentes ou nomes.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-029.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Recompensas do Baú Verdadeiro](CATALOGO-RECOMPENSAS-BAU-VERDADEIRO.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
