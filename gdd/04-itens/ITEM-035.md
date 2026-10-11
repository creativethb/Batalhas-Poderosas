---
id: "ITEM-035"
nome: "Escudo de Ferro Reforçado"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Equipamento / escudo de proteção"
raridade: "Raro"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
  - "ITEM-007"
  - "BEST-002"
imagem: "./assets/itens/ITEM-035.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Escudo de Ferro Reforçado

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-035; **coleção:** Guardião Ancestral.
- **Categoria:** Equipamento / escudo de proteção.
- **Raridade proposta:** Raro; não determina uma probabilidade de drop.
- **Nome no catálogo:** Escudo de Ferro Reforçado.
- **ID de runtime:** `escudo_ferro_reforcado`; GDD `ITEM-035`.
- **Aparência:** Escudo de ferro fosco com borda e travessas reforçadas, rebites legíveis e verso preparado para pega futura. Sem brasão novo, runas ou efeitos mágicos.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Escudo convencional de ferro reforçado, resistente e pesado.

**Descrição detalhada:** Escudo de ferro fosco com borda e travessas reforçadas, rebites legíveis e verso preparado para pega futura. Sem brasão novo, runas ou efeitos mágicos. Proteção destinada a guerreiros que enfrentavam ameaças subterrâneas, conforme proposta. Não definir exército, guerra, antigo portador ou origem especial.

## História, origem e limites narrativos

Proteção destinada a guerreiros que enfrentavam ameaças subterrâneas, conforme proposta. Não definir exército, guerra, antigo portador ou origem especial.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual após a derrota do **Guardião Ancestral do Piso 1 — BEST-002**. A chave é independente e não participa do sorteio. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Coletável individual raro do Guardião, persistente no alforge e consultável. Ainda não equipável; não substitui o Escudo de Madeira nem altera bloqueio/parry.

**Direção de design aprovada (uso disponível conforme acima):** Futuro equipamento defensivo superior ao Escudo de Madeira. A superioridade é uma direção de design, sem números, novo parry, animação ou bloqueio implementados. Preservar ITEM-007 e seu funcionamento atual.

**Dependências ainda abertas:** Encaixe, peso, proteção, durabilidade, chance e quantidade a definir.

## Comercialização e relação com NPCs

Venda e valor de referência não definidos.

John é o futuro usuário; fabricante e serviço de Cedric a definir. Nenhum novo diálogo ou receita.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-035.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Espólios do Guardião](CATALOGO-ESPOLIOS-GUARDIAO-PISO1.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
