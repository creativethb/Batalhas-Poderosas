---
id: "ITEM-030"
nome: "Relicário de Pedra"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Objeto arqueológico / comercial"
raridade: "Raro"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
imagem: "./assets/itens/ITEM-030.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Relicário de Pedra

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-030; **coleção:** Baú Verdadeiro.
- **Categoria:** Objeto arqueológico / comercial.
- **Raridade proposta:** Raro; não determina uma probabilidade de drop.
- **Nome no catálogo:** Relicário de Pedra.
- **ID de runtime:** `relicario_pedra`; GDD `ITEM-030`.
- **Aparência:** Recipiente pequeno de pedra cinzenta com tampa e entalhes discretos. Não mostrar energia, símbolos sagrados, gemas encantadas ou uma relíquia inventada no interior.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Pequeno recipiente de pedra trabalhada, preservado em câmaras antigas.

**Descrição detalhada:** Recipiente pequeno de pedra cinzenta com tampa e entalhes discretos. Não mostrar energia, símbolos sagrados, gemas encantadas ou uma relíquia inventada no interior. Objeto arqueológico de origem exata desconhecida. O nome relicário descreve a forma do recipiente e não comprova função religiosa ou conteúdo sagrado.

## História, origem e limites narrativos

Objeto arqueológico de origem exata desconhecida. O nome relicário descreve a forma do recipiente e não comprova função religiosa ou conteúdo sagrado.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual do **Baú Verdadeiro do Piso 1**. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Coletável individual raro do Baú Verdadeiro, persistente no alforge e consultável. A venda ainda não está habilitada.

**Direção de design aprovada (uso disponível conforme acima):** Futura avaliação e venda como antiguidade. Valor comercial proposto superior ao da Taça de Bronze Antiga, sem quantia definida. Não concede magia ou atributos ao jogador.

**Dependências ainda abertas:** Origem, conteúdo eventual, valor monetário e chance de obtenção a definir; não preencher esses pontos com lore inventada.

## Comercialização e relação com NPCs

Comercialização futura pela Guilda; aceitação e preço ainda não implementados.

Atendente de Espólios e Contratos e Tesouraria, no fluxo futuro da Guilda. Nenhum especialista arqueológico novo foi criado.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-030.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Recompensas do Baú Verdadeiro](CATALOGO-RECOMPENSAS-BAU-VERDADEIRO.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
