---
id: "ITEM-033"
nome: "Elmo de Bronze"
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
data_atualizacao: "2026-10-15"
---

# Elmo de Bronze

> **Estado revisto em 15/10/2026:** recompensa e uso funcional integrados ao sistema existente. Abaixo estão separados implementação, valores provisórios e funções futuras. Testes locais não equivalem a validação final ou multiplayer real.

## Identificação e aparência

- **ID:** ITEM-033; **coleção:** Guardião Ancestral.
- **Categoria:** Equipamento / proteção da cabeça.
- **Raridade proposta:** Comum; não determina uma probabilidade de drop.
- **Nome no catálogo:** Elmo de Bronze.
- **ID de runtime:** `elmo_cobre`; GDD `ITEM-033`.
- **Aparência:** Elmo de bronze com forma clara, reforços e forro interno discreto. Fabricação convencional, sem runas, poderes, transparência ou ornamentos de uma linhagem inventada.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Sem efeito mágico. Redução provisória de 5% do dano de combate enquanto equipado, aprovada para testes.

## Descrições consultáveis

**Descrição curta para o inventário:** Elmo simples de cobre trabalhado, com reforços internos.

**Descrição detalhada:** Elmo de bronze com forma clara, reforços e forro interno discreto. Fabricação convencional, sem runas, poderes, transparência ou ornamentos de uma linhagem inventada. Proteção convencional associada ao conjunto de recompensas proposto para o chefe. Fabricante e antigos usuários não definidos; não afirmar que o autômato o veste ou o produz.

## História, origem e limites narrativos

Proteção convencional associada ao conjunto de recompensas proposto para o chefe. Fabricante e antigos usuários não definidos; não afirmar que o autômato o veste ou o produz.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual após a derrota do **Guardião Ancestral do Piso 1 — BEST-002**. A chave é independente e não participa do sorteio. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual:** coletável individual do Guardião, persistente, equipável/desequipável pelo inventário no slot Cabeça. Modelo físico com escala/rotação/encaixe definidos na referência manual. Oculta o cabelo ao equipar e restaura ao desequipar. Reduz provisoriamente **5% do dano de combate**, com 95% recebido; o status acompanha a equipagem.

O nome atual é **Elmo de Bronze**, conforme correção do usuário. O ID `elmo_cobre` e ITEM-033 são preservados para compatibilidade com os saves. A arte titulada antiga pode ainda dizer Cobre: é referência histórica que precisa de revisão visual, não um segundo item. Não foi gerada uma arte substituta nesta atualização.

**Testes:** equipar/desequipar, encaixe, cabelo e status/dano conferidos localmente. Não estender os 5% a queda/armadilhas sem teste específico. Multiplayer e dispositivos físicos pendentes.

**Futuro:** balanceamento definitivo, durabilidade, peso, venda e manutenção não definidos. Não há novo efeito mágico.

## Comercialização e relação com NPCs

Possibilidade de venda e valor de compra não definidos.

John já pode equipá-lo. Serviços de Cedric para esta peça não estão definidos; não criar fabricação ou reparos nesta tarefa.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-033.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** integrado ao Studio em etapa posterior à arte inicial; encaixe/uso descritos nesta ficha. **BancoDeItens, informações, inspeção/alforge e persistência:** existentes preservados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Referência do catálogo

[Espólios do Guardião](CATALOGO-ESPOLIOS-GUARDIAO-PISO1.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
