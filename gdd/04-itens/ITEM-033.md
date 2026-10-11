---
id: "ITEM-033"
nome: "Elmo de Cobre"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Equipamento / proteção da cabeça"
raridade: "Comum"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
  - "BEST-002"
imagem: "./assets/itens/ITEM-033.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Elmo de Cobre

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-033; **coleção:** Guardião Ancestral.
- **Categoria:** Equipamento / proteção da cabeça.
- **Raridade proposta:** Comum; não determina uma probabilidade de drop.
- **Nome no catálogo:** Elmo de Cobre.
- **ID de runtime:** `elmo_cobre`; GDD `ITEM-033`.
- **Aparência:** Elmo de cobre com forma clara, reforços e forro interno discreto. Fabricação convencional, sem runas, poderes, transparência ou ornamentos de uma linhagem inventada.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Elmo simples de cobre trabalhado, com reforços internos.

**Descrição detalhada:** Elmo de cobre com forma clara, reforços e forro interno discreto. Fabricação convencional, sem runas, poderes, transparência ou ornamentos de uma linhagem inventada. Proteção convencional associada ao conjunto de recompensas proposto para o chefe. Fabricante e antigos usuários não definidos; não afirmar que o autômato o veste ou o produz.

## História, origem e limites narrativos

Proteção convencional associada ao conjunto de recompensas proposto para o chefe. Fabricante e antigos usuários não definidos; não afirmar que o autômato o veste ou o produz.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual após a derrota do **Guardião Ancestral do Piso 1 — BEST-002**. A chave é independente e não participa do sorteio. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Coletável individual do Guardião, persistente no alforge e consultável. Ainda não equipável e sem bônus de defesa.

**Direção de design aprovada (uso disponível conforme acima):** Proteção física básica, futuramente equipável na cabeça. Defesa numérica, encaixe R15, peso, durabilidade e limite de cópias não definidos. Não está equipável no jogo.

**Dependências ainda abertas:** Chance e quantidade, atributos defensivos, slot funcional e regras de venda a definir.

## Comercialização e relação com NPCs

Possibilidade de venda e valor de compra não definidos.

John é o futuro usuário. Serviços de Cedric para esta peça não estão definidos; não criar fabricação ou reparos nesta tarefa.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-033.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Espólios do Guardião](CATALOGO-ESPOLIOS-GUARDIAO-PISO1.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
