---
id: "CAT-ESPOLIOS-003"
nome: "Espólios propostos do Guardião Ancestral — Piso 1"
funcao: "Coleção documental de recompensas propostas"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-010"
  - "ITEM-033"
  - "ITEM-034"
  - "ITEM-035"
  - "ITEM-036"
  - "ITEM-037"
imagem: ""
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---
# Espólios propostos do Guardião Ancestral — Piso 1

> **ESTADO ATUAL — PARTE 2:** cadastro e recompensas aplicados no Studio. A seção histórica abaixo descreve somente a Parte 1. Tabelas, usos atuais e testes em [GAME-013](../02-gameplay/GAME-013.md).

> **HISTÓRICO DA PARTE 1 — DOCUMENTAÇÃO E ARTE.** Coleção aprovada como proposta nesta solicitação. Sem sorteio, itens funcionais, chances, preços ou nova implementação no Roblox Studio. Raridades provisórias não equivalem a chances.

| ID | Item | Categoria | Raridade proposta | Uso atual / pendência |
|---|---|---|---|---|
| [ITEM-033](ITEM-033.md) | Elmo de Bronze | Equipamento / proteção da cabeça | Comum | Equipável na cabeça; redução provisória de 5% do dano de combate. ID elmo_cobre preservado. |
| [ITEM-034](ITEM-034.md) | Peitoral de Couro | Equipamento / proteção do torso | Comum | Equipável no torso; redução numérica ainda não definida. |
| [ITEM-035](ITEM-035.md) | Escudo de Ferro Reforçado | Equipamento / escudo de proteção | Raro | Equipável na mão secundária; defesa existente. Diferencial de proteção ainda não definido. |
| [ITEM-036](ITEM-036.md) | Candelabro de Expedição | Equipamento utilitário / iluminação portátil | Raro | Lançar pela bolsa, iluminar e recolher; danifica no terceiro recolhimento. Reparo/sucata futuros. |
| [ITEM-037](ITEM-037.md) | Pernil Assado | Consumível / alimento substancial | Raro | USAR consome uma unidade e cura 100% da vida máxima, sem ultrapassar o máximo. Produção futura. |

## Chefe e origem das recompensas

Referência existente: BEST-002 — Autômato de Pedra / Guardião do Piso 1, modelo Golem_Pedra. A denominação Guardião Ancestral nesta proposta não cria outro chefe nem fixa seu nome próprio. Proteções e objetos são recompensas associadas ao encontro; não são partes anatômicas confirmadas de um autômato. A presença do Pernil no conjunto exige futura justificativa narrativa, sem atribuir carne à criatura.

## Chave de progressão preservada

A Chave do Guardião (`chave_guardiao_andar1`) já pertence à progressão, conforme DNG-003 e DNG-006. É liberada após a derrota e consumida no mecanismo da saída; não integra este sorteio. A persistência temporária e o fluxo atual não foram alterados. Não foi localizada ficha ITEM exclusiva da chave: preservam-se os registros existentes, sem inventar um ID duplicado.

## Equipamentos e manutenção

Elmo de Bronze e Peitoral de Couro são convencionais, sem poderes novos. Os três equipamentos usam o sistema existente. Superioridade numérica do escudo ainda é direção de design; ver ITEM-033–035.

Candelabro: posicionar → iluminar → recolher → reposicionar; após três posicionamentos, o terceiro recolhimento o torna danificado e persistente. Cedric poderá restaurá-lo e a Guilda poderá comprá-lo como sucata, sem serviços ou preços ativos.

## Exclusões

Elmo de Vidro não é recompensa deste chefe. As três ideias anteriores de materiais minerais do Guardião no catálogo de espólios eram backlog editorial, sem cadastro funcional; não são adicionadas automaticamente a esta coleção. Chances, quantidades e limites provisórios já estão em GAME-013; balanceamento definitivo e novas vendas continuam pendentes.

## Estado visual e funcional

Cada ficha tem uma imagem própria em `./assets/itens/ITEM-XXX.png`, com o nome dentro da arte e identidade da Oficina de Cedric. As artes de ITEM-033 a ITEM-037 foram produzidas e conferidas em 1672 × 941; aprovação artística final ainda pendente. Modelos dos equipamentos e candelabro já foram integrados; inventário, sorteio e usos atuais estão nas fichas. Novas vendas, manutenção e balanceamento definitivo permanecem pendentes.

[Consolidação e auditoria](../07-masmorras/DNG-014.md).


## Atualização funcional — Parte 2, 11/10/2026

A etapa documental anterior é preservada como histórico. A Parte 2 autorizou e aplicou sorteio individual, coleta seletiva e persistência no Studio. [GAME-013](../02-gameplay/GAME-013.md) registra configuração provisória, regras, scripts, testes e pendências.

Baús contam a primeira coleta efetiva por encontro; o Guardião reserva o rendimento na vitória dos participantes elegíveis, mesmo sem coleta imediata. Os contadores são independentes e renovam à meia-noite de Brasília. Moedas vão à carteira existente. A Bolsa de Moedas Antigas é a representação desse crédito direto, sem um segundo recipiente remunerado. A chave de progressão segue independente e o Elmo de Vidro continua excluído.

Ração, Bandagem e Pernil possuem consumo e cura; o Fragmento registra leitura no Diário sem consumir o papel. Elmo de Bronze, Peitoral de Couro e Escudo de Ferro Reforçado são equipáveis; o candelabro tem lançamento, luz, coleta e desgaste. Óleo sem abastecimento funcional; manutenção, novas vendas e investigação continuam futuras. Detalhes e limites em GAME-013/ITEM-033–036. TESTADO localmente não equivale a VALIDADO.
