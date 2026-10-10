---
id: "GAME-012"
nome: "Economia da masmorra e atendimento da Guilda de Arkan"
funcao: "Venda de materiais, comprovantes persistentes e pagamentos na carteira existente"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra / alforge / Guilda de Arkan"
relacionados:
  - "GAME-009"
  - "GAME-011"
  - "ITEM-008"
  - "ITEM-022"
imagem: ""
atualizado_por: "Codex"
data_atualizacao: "2026-10-09"
---

# Economia da masmorra e da Guilda de Arkan

**IMPLEMENTADO / TESTADO EM PLAY LOCAL E DATASTORE REAL ISOLADO.** Primeira versão funcional, com valores provisórios autorizados pelo responsável. Não equivale a VALIDADO, economia definitiva ou publicação do place.

## Ciclo disponível

Criaturas comuns do Piso 1 → inspeção compartilhada de GAME-011 → coleta seletiva → alforge persistente → entrega à Guilda → comprovante pendente → recebimento na Tesouraria → carteira existente.

Os 15 materiais ITEM-008–022 já cadastrados são aceitos. Baú Falso, Guardião e outros pisos não recebem novos espólios. As probabilidades e o sorteio adicional do Vesplume permanecem iguais.

## Três postos

| Posto | Local atual | Atendimento implementado |
|---|---|---|
| Recepção | Balcão principal do térreo | Apresenta os serviços e indica os setores. |
| Espólios e Contratos | Segundo andar do anexo | Catálogo de materiais aceitos, quantidade possuída, miniatura, raridade, informações, preço, seleção unitária/lote e confirmação de entrega. Contratos indisponíveis. |
| Tesouraria | Balcão próprio no mezanino | Lista de comprovantes pendentes/pagos; recebimento por entrega ou de todos os pendentes; consulta à carteira. |

Utiliza os três protótipos R15 já existentes em Workspace.Vila.08_GuildaDeArkham_V2.12_Atendentes_Prototipos. Lina, Mara e Celia são somente nomes provisórios de implementação, sem biografia ou personalidade canonizada. Nenhum NPC adicional.

Interação E no PC, X no controle, botão nativo de toque; jogador vivo, perfil carregado e distância máxima de 12 studs. Atendimento fecha ao sair do alcance. BP_UIState impede sobreposição com as demais telas; Informações abre ficha independente e oculta a lista anterior. Interface ampla/estreita com rolagem e seleção numérica, +/− e Todos.

## Tabela de compra provisória

PREÇOS DE TESTE. Fonte única: ReplicatedStorage.GuildaEconomiaConfig.Precos. Unidades de cobre; nenhum imposto, tarifa ou margem adicional.

| Ficha | Material | Cobre por unidade |
|---|---|---:|
| ITEM-008 | Secreção Luminescente | 4 |
| ITEM-009 | Membrana de Vesplume | 6 |
| ITEM-010 | Glândula Luminosa | 35 |
| ITEM-011 | Esporos de Grumelo | 3 |
| ITEM-012 | Fibra Fúngica | 5 |
| ITEM-013 | Núcleo de Esporos | 30 |
| ITEM-014 | Fragmento de Rocha | 4 |
| ITEM-015 | Cascalho Mineral | 5 |
| ITEM-016 | Coração de Pedra | 35 |
| ITEM-017 | Pena de Correnteza | 5 |
| ITEM-018 | Essência de Brisa | 6 |
| ITEM-019 | Cristal de Corrente Ascendente | 40 |
| ITEM-020 | Placa de Carapaça | 5 |
| ITEM-021 | Quitina Resistente | 7 |
| ITEM-022 | Placa Intacta de Cascudo | 40 |


A carteira permanece em cobre: **10 cobres = 1 prata; 100 pratas = 1 ouro = 1.000 cobres**. Não há nova carteira, conversão paralela ou inventário. Cadastro de material/preço possibilita expansão a outros pisos, sem criar uma interface por piso; somente itens realmente cadastrados e implementados podem ser vendidos.

## Entrega e pagamento

1. Selecionar uma ou várias espécies de material e quantidades reais.
2. Revisar cotação calculada no servidor, válida por 120 segundos.
3. Confirmar: o servidor verifica novamente preços e inventário, retira exatamente as quantidades e registra uma entrega PENDENTE.
4. Exibir comprovante numerado, valor e materiais entregues.
5. Na Tesouraria, receber uma entrega ou todas as pendentes. O servidor credita a carteira e marca os comprovantes PAGOS na mesma gravação.

Cancelar antes de confirmar não altera inventário, carteira ou comprovantes. Após confirmar a entrega, o comprovante pode ser consultado mesmo depois de reconectar. Repetir um pagamento já recebido não credita novamente. A interface envia IDs de cotação/comprovantes, nunca um valor autorizado pelo cliente.

Uma entrega confirmada em recuperação não pode ser apresentada como cancelada: o atendimento informa a gravação pendente. Se já estiver gravada, apresenta o comprovante existente e orienta a retirada na Tesouraria.

Preços alterados entre cotação e confirmação exigem nova cotação. Comprovantes entregues preservam os valores negociados. Carteira no limite mantém o pagamento pendente; é possível liquidar entregas individualmente. Limites técnicos configuráveis: carteira 1 bilhão de cobres, até 100 entregas pendentes e histórico das últimas 100 pagas, além do acumulado e da sequência. Não são parâmetros de economia definitiva.

## Persistência e segurança implementadas

PersistenciaService extrai e centraliza o código do GerenciadorPersistenciaServer, mantendo BP_DataStore_V1/Jogador_UserId, TemplateDados, campos antigos e desconhecidos. Inventário, Economia.Carteiras e Economia.Guilda.Entregas são gravados juntos em **um UpdateAsync do mesmo perfil**; nenhuma chave separada para pagamentos.

Mutação prepara uma cópia sem efeitos em runtime. A entrega/pagamento trava as mutações econômicas do InventarioService durante a gravação. Somente após sucesso os atributos são aplicados e a interface atualizada. O recibo inclui ID, sequência, linhas com quantidade/preço/subtotal, total, estado e horários.

Token persistido torna a repetição de uma escrita idempotente em caso de resposta perdida. Depois de três falhas, mantém a trava e tenta recuperação em segundo plano; não permite uma segunda retirada/crédito enquanto o resultado é incerto. A reconexão carrega o estado durável do perfil.

Sessão exclusiva por perfil, com lease de 180 s, renovação/autosalvamento a cada 30 s e liberação no encerramento. Uma segunda sessão não pode sobrescrever a sessão ativa; entrada aguarda acesso seguro. Perda de propriedade da sessão impede novas operações. Autosave e encerramento utilizam o mesmo controle de gravação.

Servidor rejeita valores fracionários, negativos, zero, NaN/infinito, excesso, itens não aceitos, inventário insuficiente, cotação inválida/expirada e comprovantes falsos/repetidos. Valida posto, distância, vida e perfil; pedidos têm limite de frequência. Pagamento não depende de variáveis temporárias de atendimento.

## Scripts e módulos

- GuildaEconomiaConfig: preços e limites centralizados.
- GuildaEconomiaService: cotação, entrega, recebimento e consulta.
- GuildaEconomiaServer: três prompts, sessões e remotos autorizados.
- GuildaEconomiaClient: catálogo, revisão/cancelamento, recibos e Tesouraria.
- PersistenciaService + bootstrap GerenciadorPersistenciaServer: perfil único, sessão, gravação/recovery.
- InventarioService: trava econômica e aplicação do resultado durável; APIs anteriores mantidas.
- TemplateDados: estrutura reconciliável Economia.Guilda.
- BancoDeItens: usos atuais/destinos comerciais consultáveis, derivados da configuração única.

BP_ItemInterface/BP_UITheme/BP_UIState, EspoliosConfig/EspoliosService, GerenciadorComercioServer, padaria e controladores de combate preservados.

## Testes efetivamente executados

- Perfis isolados com simulação de DataStore: venda unitária e lote, 15 materiais, total adulterado, inventário insuficiente, valores inválidos, cotação sem confirmação, repetição de entrega/pagamento, dois pedidos simultâneos e limite de carteira.
- Falha antes de gravar, resposta perdida após gravar, três falhas seguidas e recuperação em segundo plano; nenhuma segunda retirada/crédito. Save concorrente e mutação de inventário durante gravação recusados.
- Cancelamento sob falha: cotação ainda não confirmada pôde ser cancelada; durante recuperação foi recusado; após gravação apresentou a entrega existente sem prometer devolução ou criar outra venda.
- Sessões concorrentes impedidas; encerramento e reabertura recuperaram inventário e pendências.
- Resposta tardia após troca simulada de sessão: servidor anterior manteve as mutações bloqueadas; a nova sessão recuperou exatamente a entrega gravada e seu pagamento pendente.
- **DataStore real BP_DataStore_V1, chave exclusiva de teste:** entrega de dois esporos por 6 cobres, encerramento e nova sessão, pendência recarregada; pagamento, outra nova sessão com saldo 6 e pendência zero; replay após reabertura não duplicou. Chave isolada removida ao concluir.
- PC: três atendimentos via E; seleção de 1 Secreção e 3 Membranas por 22 cobres, cancelar preservando tudo, confirmar/receber com cliques reais, recibo e atualização de carteira. Informações ocultou a lista e exibiu preço/uso comercial corretos.
- Conferência final: perfil real recarregou com itens/moedas originais; uma entrega de teste de 3 cobres foi recebida pelo botão individual da Tesouraria e posteriormente removida pela restauração da fixture.
- Layout conferido em captura ampla e janela de 320 px; sem teste em aparelho físico.
- Regressão: 1.000 sorteios por espécie comum; Vesplume registrou corpo único, inspeção e coleta parcial. Trava econômica recusou coleta sem consumir espólio; mesma revisão coletou após liberação; replay recusado.
- Padaria real: ComprarProduto comprou dois pães por 16 cobres; quantidade e carteira atualizadas.
- Perfil, itens e moedas da conta real restaurados ao final das fixtures; nenhuma recompensa de teste mantida.

O primeiro ensaio de DataStore isolado usou uma chave longa demais e foi recusado antes da gravação; corrigido o identificador de teste, as seis verificações reais passaram. Isso não alterou a chave de produção.

## Pendências e limites

Dois clientes reais, troca entre servidores publicados, interrupção física do servidor durante UpdateAsync e dispositivos físicos de toque/controle continuam pendentes. Concorrência por tarefas e sessões isoladas não equivale a multiplayer real. A reabertura testada no DataStore real ocorreu por novas instâncias do serviço dentro do Studio.

Contratos completos, fabricação, aluguel, banco, empréstimos, economia definitiva, novos itens/pisos e personalidades das atendentes não implementados. Não houve nova travessia completa do Guardião/Piso 2; combate não foi alterado. Place editado no Studio; publicação do Roblox não executada nesta etapa.

index.html, renderizador e arquitetura do mini-site preservados.
