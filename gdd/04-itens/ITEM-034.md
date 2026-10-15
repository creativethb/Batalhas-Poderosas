---
id: "ITEM-034"
nome: "Peitoral de Couro"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Equipamento / proteção do torso"
raridade: "Comum"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
  - "ITEM-005"
  - "BEST-002"
imagem: "./assets/itens/ITEM-034.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Peitoral de Couro

> **Estado revisto em 15/10/2026:** recompensa e uso funcional integrados ao sistema existente. Abaixo estão separados implementação, valores provisórios e funções futuras. Testes locais não equivalem a validação final ou multiplayer real.

## Identificação e aparência

- **ID:** ITEM-034; **coleção:** Guardião Ancestral.
- **Categoria:** Equipamento / proteção do torso.
- **Raridade proposta:** Comum; não determina uma probabilidade de drop.
- **Nome no catálogo:** Peitoral de Couro.
- **ID de runtime:** `peitoral_couro`; GDD `ITEM-034`.
- **Aparência:** Peitoral de couro marrom em painéis costurados, fivelas simples e tiras ajustáveis. Exibido vazio, sem personagem ou corpo de manequim.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Proteção de couro reforçado com costuras e tiras ajustáveis.

**Descrição detalhada:** Peitoral de couro marrom em painéis costurados, fivelas simples e tiras ajustáveis. Exibido vazio, sem personagem ou corpo de manequim. Armadura de fabricação convencional para proteção inicial. Não está ligada às Inscrições da Forja nem substitui o Peitoral de Vidro de Cedric.

## História, origem e limites narrativos

Armadura de fabricação convencional para proteção inicial. Não está ligada às Inscrições da Forja nem substitui o Peitoral de Vidro de Cedric.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual após a derrota do **Guardião Ancestral do Piso 1 — BEST-002**. A chave é independente e não participa do sorteio. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual:** recompensa individual persistente; pode equipar/desequipar no torso pelo inventário existente. Modelo `BP_PeitoralCouro_Modelo`, acessório/attachment com vínculo ao corpo, escala e orientação ajustadas manualmente. Não substitui o Peitoral de Vidro (ITEM-005).

**Defesa numérica:** ainda não definida; equipagem visual funcional não autoriza inventar porcentagem de redução ou penalidade de movimento.

**Testes locais:** idle, caminhada, ataque, guarda, equipagem repetida sem duplicação e recusa sem posse. Os ajustes posteriores de tamanho foram manuais; clipping em todas as animações e dispositivos físicos continuam sujeitos a avaliação. Venda, durabilidade, fabricação e reparo são futuros.

## Comercialização e relação com NPCs

Venda, comprador e preço permanecem a definir.

John já pode equipá-lo. Fabricante e serviços de oficina para essa peça não foram definidos.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-034.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** integrado ao Studio em etapa posterior à arte inicial; encaixe/uso descritos nesta ficha. **BancoDeItens, informações, inspeção/alforge e persistência:** existentes preservados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Espólios do Guardião](CATALOGO-ESPOLIOS-GUARDIAO-PISO1.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
