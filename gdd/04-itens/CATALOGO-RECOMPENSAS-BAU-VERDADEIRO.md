---
id: "CAT-ESPOLIOS-002"
nome: "Recompensas propostas do Baú Verdadeiro — Piso 1"
funcao: "Coleção documental de recompensas propostas"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-010"
  - "ITEM-026"
  - "ITEM-027"
  - "ITEM-028"
  - "ITEM-029"
  - "ITEM-030"
  - "ITEM-031"
  - "ITEM-032"
imagem: ""
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---
# Recompensas propostas do Baú Verdadeiro — Piso 1

> **ESTADO ATUAL — PARTE 2:** cadastro e recompensas aplicados no Studio. A seção histórica abaixo descreve somente a Parte 1. Tabelas, usos atuais e testes em [GAME-013](../02-gameplay/GAME-013.md).

> **HISTÓRICO DA PARTE 1 — DOCUMENTAÇÃO E ARTE.** Coleção aprovada como proposta nesta solicitação. Sem sorteio, itens funcionais, chances, preços ou nova implementação no Roblox Studio. Raridades provisórias não equivalem a chances.

| ID | Item | Categoria | Raridade proposta | Finalidade proposta |
|---|---|---|---|---|
| [ITEM-026](ITEM-026.md) | Ração de Explorador | Consumível / alimento de expedição | Comum | Consumir para restaurar 25% da vida máxima, limitado à vida máxima do personagem. O consumo, a interface e a aplicação da cura ainda não foram implementados. |
| [ITEM-027](ITEM-027.md) | Bandagem de Campo | Consumível / primeiros socorros | Comum | Consumir para restaurar 15% da vida máxima, respeitando o limite de HP. Não cura venenos, infecções nem efeitos especiais. Nenhuma dessas ações está funcional nesta etapa. |
| [ITEM-028](ITEM-028.md) | Bolsa de Moedas Antigas | Recompensa monetária / recipiente | Comum | Representar uma recompensa monetária que poderá conter cobre e prata, com possibilidade rara de ouro. Quantias, chance de ouro e forma de abertura ficam a definir. Não cria outra carteira ou moeda. |
| [ITEM-029](ITEM-029.md) | Taça de Bronze Antiga | Objeto comercial / antiguidade | Comum | Objeto comercial destinado principalmente à futura venda na Guilda de Arkan. Seu interesse comercial deriva do material e da antiguidade; não possui poder especial conhecido. |
| [ITEM-030](ITEM-030.md) | Relicário de Pedra | Objeto arqueológico / comercial | Raro | Futura avaliação e venda como antiguidade. Valor comercial proposto superior ao da Taça de Bronze Antiga, sem quantia definida. Não concede magia ou atributos ao jogador. |
| [ITEM-031](ITEM-031.md) | Fragmento de Registro Antigo | Documento narrativo / objeto comercial | Raro | Leitura futura desbloqueia conhecimento permanente no Diário de John. O papel físico poderá continuar no alforge e ser vendido depois; vender ou perder o papel não deverá apagar o conhecimento já registrado. Leitura, memória e venda deste item ainda não foram implementadas. |
| [ITEM-032](ITEM-032.md) | Frasco de Óleo para Lamparina | Suprimento / utilitário de iluminação | Comum | Abastecer equipamentos de iluminação quando existir um sistema compatível. Consumo, capacidade e equipamentos receptores não foram implementados. Não abastece automaticamente o Cordão Luminoso. |

## Identidade e preservação

Suprimentos, consumíveis, objetos comerciais, documento e utilitário de expedição. Não repetir os alimentos existentes da Padaria nem ITEM-008 a ITEM-025, associados a criaturas comuns ou ao Baú Falso. O Elmo de Vidro não entra neste catálogo.

Os valores de cura são direções aprovadas documentalmente: Ração 25% e Bandagem 15% da vida máxima, limitadas ao HP máximo. Bandagem não remove veneno, infecção nem efeitos especiais. Não implementar consumo, animações ou novos botões nesta etapa.

## Bolsa e moedas

A Bolsa de Moedas Antigas representa cobre e prata com possibilidade rara de ouro. Não definir quantia nem chance. A implementação futura escolherá recipiente coletável OU representação de crédito direto, impedindo duplicação do mesmo conteúdo. Preservar a carteira única existente e sua conversão; não inventar denominações antigas ou preço adicional da bolsa.

## Papel e descoberta

ITEM-031 é legível e comercializável por proposta. O conhecimento deve ser registrado permanentemente no Diário antes de uma eventual venda do documento físico, sem vincular a permanência da descoberta à posse do papel. Texto e limites canônicos em DOS-005.

## Comércio e iluminação

Taça e Relicário têm venda futura prevista na Guilda; o Relicário deve ter valor superior à Taça, sem números agora. Óleo não entra no sistema de iluminação até existir compatibilidade definida; não substitui o Fluido Luminescente de ITEM-006.

## Estado visual e funcional

Cada ficha tem uma imagem própria em `./assets/itens/ITEM-XXX.png`, com o nome dentro da arte e identidade da Oficina de Cedric. As artes de ITEM-026 a ITEM-032 foram produzidas e conferidas em 1672 × 941; aprovação artística final ainda pendente. Inventário, sorteio, coleta e usos de consumo/leitura foram integrados pela Parte 2. Novas vendas, abastecimento e funções não descritas nas fichas permanecem futuras. A arte conceitual não certifica um modelo físico individual de cada material.

[Consolidação e auditoria](../07-masmorras/DNG-014.md).


## Atualização funcional — Parte 2, 11/10/2026

A etapa documental anterior é preservada como histórico. A Parte 2 autorizou e aplicou sorteio individual, coleta seletiva e persistência no Studio. [GAME-013](../02-gameplay/GAME-013.md) registra configuração provisória, regras, scripts, testes e pendências.

Baús contam a primeira coleta efetiva por encontro; o Guardião reserva o rendimento na vitória dos participantes elegíveis, mesmo sem coleta imediata. Os contadores são independentes e renovam à meia-noite de Brasília. Moedas vão à carteira existente. A Bolsa de Moedas Antigas é a representação desse crédito direto, sem um segundo recipiente remunerado. A chave de progressão segue independente e o Elmo de Vidro continua excluído.

Ração, Bandagem e Pernil possuem consumo e cura; o Fragmento registra leitura no Diário sem consumir o papel. Elmo de Bronze, Peitoral de Couro e Escudo de Ferro Reforçado são equipáveis; o candelabro tem lançamento, luz, coleta e desgaste. Óleo sem abastecimento funcional; manutenção, novas vendas e investigação continuam futuras. Detalhes e limites em GAME-013/ITEM-033–036. TESTADO localmente não equivale a VALIDADO.
