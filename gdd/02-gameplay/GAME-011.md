---
id: "GAME-011"
nome: "Inspeção, espólios compartilhados e informações de itens"
funcao: "Coleta seletiva autoritativa integrada ao alforge e à carteira"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1 / bolsa de John"
relacionados:
  - "BEST-017"
  - "ITEM-008"
  - "ITEM-009"
  - "ITEM-010"
  - "GAME-009"
  - "GAME-010"
  - "DNG-013"
atualizado_por: "Codex"
data_atualizacao: "2026-10-08"
---

# Inspeção e espólios compartilhados

## Escopo e arquitetura implementados

Somente **Vesplume** está habilitado. Os demais inimigos, baús, Guardião e Piso 2 não receberam espólios nesta etapa. Nenhuma loja, fabricação, melhoria, contrato ou economia definitiva foi criada.

BancoDeItens continua sendo o catálogo central. ITEM-008/009/010 acrescentam metadados separados da interface: origem, propriedades, descrições, usos atuais/futuros e destinos. IDs de runtime permanecem estáveis.

EspoliosConfig define probabilidades e quantidades. EspoliosService mantém uma tabela no servidor por instância derrotada, com GUID, revisão e observadores. EspoliosServer recebe apenas coleta/fechamento; o prompt autoriza a inspeção.

InventarioService.Transact existente transfere materiais e moedas sem yield após pré-validação de todos os saldos. Atributos, sincronização da bolsa e BP_DataStore_V1 permanecem a arquitetura única. Nenhum inventário ou DataStore paralelo.

## Sorteio provisório

Resultado único por corpo; reabrir, fechar ou desconectar nunca sorteia novamente.

1. **20% de vazio forçado**, sem material nem moeda.
2. Nos 80% restantes, entradas independentes:

| Entrada | Chance condicional | Quantidade |
|---|---:|---:|
| Secreção Luminescente | 55% | 1–3 |
| Membrana de Vesplume | 40% | 1–3 |
| Glândula Luminosa | 8% | 1 |
| Cobre | 50% | 1–10 |
| Prata | 12% | 1–2 |

Após passar pelo vazio, teste adicional independente de **2%** garante 10 cobres e 2 pratas; materiais podem acompanhar. Falhas simultâneas das entradas também produzem vazio. Chance total teórica de absolutamente nada: **28,5688064%**. O prêmio máximo garantido pelo teste adicional representa 1,6% dos sorteios; a combinação máxima também pode surgir pelas entradas normais.

Todas as probabilidades, contagens e moedas são **DE TESTE**, ajustáveis em EspoliosConfig.

A carteira existente usa cobre: 10 cobres equivalem a 1 prata; 1.000 cobres a 1 ouro. Preservado esse formato, 10 cobres + 2 pratas creditam 30 unidades de cobre. Nenhum saldo paralelo de prata.

## Derrota e inspeção

Voo/IA param; luz apaga. A derrota anterior era dissolução de 0,5 s seguida de destruição. Para permitir inspeção, a dissolução final foi adiada: o modelo original pousa inerte e recolhe as asas durante a transição. Rig, vida, ataques e voo foram preservados.

Prompt **Inspecionar**, 10 studs, jogador vivo e perfil carregado: E no PC, X no controle e botão contextual de toque/clique. Ignora o sistema de conversa da vila.

John realiza gesto procedural breve de observação, compatível com Motor6D/AnimationConstraint, sem âncora, teleporte ou mudança de velocidade. Movimento interrompe o gesto. Com arma sacada, preserva os braços e usa cabeça/cintura. Nenhum ID de animação fictício.

A galeria local Mixamo foi conferida: seu manifesto contém 51 animações de espada/escudo, sem entrada específica de inspeção ou coleta. Os agachamentos disponíveis não foram remapeados para essa função. Animação dedicada permanece para refinamento futuro autorizado pelo responsável.

## Interface e bolsa

Janela de espólios com miniatura, nome, quantidade, raridade e prévia. Clique/toque/comando seleciona o tipo; +/− ajustam quantidades. **Coletar** transfere somente a seleção. **Deixar/Fechar** preservam o restante.

**Informações** abre ficha independente mais ampla, com miniatura maior. A bolsa/lista anterior fica oculta; voltar restaura o contexto do mesmo item. BP_ItemInterface compartilha a apresentação; BP_UIState/BP_UITheme existentes coordenam exclusividade/paleta.

Miniaturas vetoriais nativas representam amostra luminosa em vidro, fragmento de asa com nervuras e glândula com ducto/núcleo. Também aparecem na bolsa. Sem drops físicos individuais ou assets fictícios.

Layout usa a área da ScreenGui e respeita inset; no toque, +/− têm 44 px. Controle possui foco dourado, A para ativar, B para voltar/fechar e stick direito para rolar a ficha. Transição/som discreto. A base aceita futuros equipamentos/consumíveis/diário, sem adicionar seus conteúdos agora.

## Segurança e grupo

**Um conjunto compartilhado por corpo**, sem cópias individuais.

Servidor exige inscrição na inspeção, GUID válido, corpo disponível, distância, jogador vivo e perfil carregado. IDs devem existir no resultado; quantidades devem ser inteiros positivos finitos, não superiores ao disponível; até cinco entradas.

Retirada/crédito são síncronos, sem rede/DataStore entre validação e commit. Revisão incrementada recusa replay/pedidos antigos; trava evita reentrada. Falha de capacidade/saldo não consome o resultado. Todos os observadores recebem atualização. Fechar/desconectar remove apenas a própria inspeção.

Estrutura aceita cinco/seis participantes sem usuários fixos. **Multiplayer real não testado**; concorrência de duas tarefas do mesmo jogador não equivale a dois clientes.

## Encerramento de sala e sessão

Piso 1 não tinha evento individual de conclusão de sala. Encerramento dos espólios exige: nenhum inimigo vivo da sala, nenhum jogador na área do trigger com margem de 8 studs, nenhum inspetor ativo, **15 s** consecutivos de área vazia e **20 s** mínimos desde a última derrota. EspoliosEncerrados marca conclusão.

Sair sozinho não remove corpos enquanto alguém permanece próximo ou inspeciona. Após encerramento, corpo afunda 4 studs em 0,85 s; espólios abandonados, conexões e referências são descartados.

Saída do último jogador reutiliza o critério existente do gerador, personagens vivos abaixo de Y = −20. EncerrarSessao antecede destruição com afundamento. Regeneração encerra sessão anterior e adia remoção em 0,9 s. Esse critério legado não cria grupos ou balanceamento novo.

## Testes efetivamente executados

- Play com modelo real: vazio, só moedas, só material, combinação completa; configuração temporária restaurada.
- 10.000 sementes: 2.769 vazios, 1.151 só moedas, 2.588 só materiais, 3.492 mistos; 185 combinações máximas de moedas. Quantidades dentro dos limites.
- Coleta 1 de 3, fechar/reabrir, coletar 2 restantes; GUID preservado.
- Duas tarefas concorrentes do mesmo jogador/revisão: somente uma retirada aceita.
- Replay, IDs falsos, excesso, zero, NaN, infinito e distância rejeitados.
- Falha no limite técnico da bolsa não retirou o espólio; depois de liberar capacidade, a mesma revisão permitiu recolhê-lo.
- 10 cobres + 2 pratas creditam 30 cobres; Export/Import preserva materiais.
- Prompt cliente-servidor/tecla E; cliques nos seletores, coleta, bolsa, informações/retorno. Bolsa oculta na ficha; volta ao mesmo item.
- Gesto alterou transform do rig atual sem âncora ou alteração de velocidade.
- Espada real: Vesplume de 90 de vida derrotado após cinco impactos de 22; corpo/prompt permaneceram.
- Corpo permaneceu 21 s com John na sala; saída provocou encerramento, afundamento e remoção.
- Ficha conferida com conteúdo rolável e rodapé separado em 329×568, 700×300 e 700×483; troca efetiva de contêiner estreito/amplo restaurou tipografia e miniatura. Isso é teste de layout, sem equivaler a aparelho físico.

## Pendências

Dois clientes simultâneos, cinco/seis jogadores, saída de um enquanto outro permanece, latência/desconexão entre clientes, toque físico e gamepad físico ainda dependem de ambiente adequado. Input virtual recusou ButtonB reservado ao CoreGui; isso não valida controle físico.

Export/Import exercitado; salvar/recarregar entre servidores reais não foi forçado. Perfil/moedas dos testes foram restaurados. Não houve nova travessia completa de Guardião/Piso 2; nenhum de seus controladores foi modificado.

Estado: **IMPLEMENTADO / TESTADO EM PLAY LOCAL**, distinto de VALIDADO pelo responsável. Balanceamento, economia e arte definitiva continuam em desenvolvimento.
