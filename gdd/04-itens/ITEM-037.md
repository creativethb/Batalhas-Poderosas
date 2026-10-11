---
id: "ITEM-037"
nome: "Pernil Assado"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Consumível / alimento substancial"
raridade: "Raro"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
  - "BEST-002"
imagem: "./assets/itens/ITEM-037.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Pernil Assado

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-037; **coleção:** Guardião Ancestral.
- **Categoria:** Consumível / alimento substancial.
- **Raridade proposta:** Raro; não determina uma probabilidade de drop.
- **Nome no catálogo:** Pernil Assado.
- **ID de runtime:** `pernil_assado`; GDD `ITEM-037`.
- **Aparência:** Pernil assado com osso curto exposto e tonalidades quentes de alimento preparado. Peça isolada, sem personagem ou prato decorativo inventado.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Alimento substancial para recuperar as forças após combates difíceis.

**Descrição detalhada:** Pernil assado com osso curto exposto e tonalidades quentes de alimento preparado. Peça isolada, sem personagem ou prato decorativo inventado. Provisão proposta no conjunto de recompensas do chefe. Não é parte orgânica do autômato; a relação narrativa exata entre o alimento e o encontro será definida depois.

## História, origem e limites narrativos

Provisão proposta no conjunto de recompensas do chefe. Não é parte orgânica do autômato; a relação narrativa exata entre o alimento e o encontro será definida depois.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual após a derrota do **Guardião Ancestral do Piso 1 — BEST-002**. A chave é independente e não participa do sorteio. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Coletável individual raro do Guardião, persistente no alforge. USAR consome uma unidade e restaura 100% da vida máxima, limitada ao máximo. Produção e venda na vila permanecem futuras.

**Direção de design aprovada (uso disponível conforme acima):** Consumir para restaurar 100% da vida máxima, sem ultrapassar o limite de HP. Futuramente poderá ser produzido em outros sistemas da vila; não deve ser exclusivo do Guardião para sempre. Cura implementada; produção futura ainda não implementada.

**Refinamento futuro:** duração de animação de consumo e regras especiais em combate ainda não definidas; quantidade e obtenção provisórias estão em GAME-013.

## Comercialização e relação com NPCs

Possibilidade de venda e preço permanecem a definir.

John é o usuário. Não atribuir produção à Padaria, à Fazenda ou a outro NPC nesta etapa.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-037.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Espólios do Guardião](CATALOGO-ESPOLIOS-GUARDIAO-PISO1.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
