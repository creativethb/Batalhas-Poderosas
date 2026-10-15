---
id: "GAME-013"
nome: "Recompensas individuais, coleta e persistência do Piso 1"
funcao: "Sorteio de tesouros, rendimento diário e concessão persistente"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1 / alforge e carteira de John"
relacionados:
  - "GAME-009"
  - "GAME-010"
  - "GAME-011"
  - "GAME-012"
  - "DNG-003"
  - "DNG-006"
  - "DNG-014"
  - "BEST-002"
  - "CAT-ESPOLIOS-002"
  - "CAT-ESPOLIOS-003"
  - "DOS-005"
  - "ITEM-026"
  - "ITEM-027"
  - "ITEM-028"
  - "ITEM-029"
  - "ITEM-030"
  - "ITEM-031"
  - "ITEM-032"
  - "ITEM-033"
  - "ITEM-034"
  - "ITEM-035"
  - "ITEM-036"
  - "ITEM-037"
  - "ITEM-038"
imagem: ""
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Recompensas individuais do Piso 1 — Parte 2

Implementação aplicada no Studio da vila, place `82288539700831`, em 11/10/2026. Estado: **EM_DESENVOLVIMENTO / TESTADO nos cenários abaixo**, sem declaração de validação final ou publicação do place. As tabelas são provisórias para testes. Os catálogos e artes da Parte 1 foram consultados; nenhum novo item ou prefab foi criado.

## Ciclo e elegibilidade

Baú Verdadeiro: cada jogador tem resultado próprio por baú físico e geração da masmorra. Abrir revela o baú para todos; recolher não elimina o direito dos demais. Inspeção sem coleta não gasta o limite. O primeiro recolhimento efetivo reserva a etapa diária, e recolhimentos parciais posteriores não a gastam novamente.

Guardião: cada participante elegível recebe resultado próprio por derrota física. A vitória reserva resultado e etapa diária no perfil, mesmo sem inspeção ou coleta imediata; novas inspeções não repetem a vitória. Elegibilidade provisória: personagem vivo dentro dos limites da arena por pelo menos 3 segundos, com presença nos últimos 12 segundos antes da derrota. O conjunto elegível fica fixo na derrota; chegar depois não concede espólios. Não há exigência nova de dano mínimo.

Categorias `BauVerdadeiro` e `GuardiaoAncestral` têm contadores independentes por jogador e piso. A chave continua no sistema original, fora do sorteio e do limite diário. A quarta vitória não impede a obtenção/uso da chave nem a progressão. O Baú Falso conserva seu encontro e espólios compartilhados; não recebe estes itens. O Elmo de Vidro — ITEM-038 — não é cadastrado nem sorteado por esta implementação.

## Valores monetários provisórios

| Categoria | Etapa diária | Cobre | Prata | Ouro | Itens adicionais |
|---|---|---|---|---|---|
| Baú Verdadeiro | 1ª coleta | 15–30 | 2–4 | 2% de 1 | até 2 diferentes; verificações de slot 75% e 35% |
| Baú Verdadeiro | 2ª coleta | 5–10 | 1 | nenhum | até 1 comum; slot 40% |
| Baú Verdadeiro | 3ª coleta | 1–3 | nenhum | nenhum | nenhum |
| Baú Verdadeiro | 4ª e seguintes | nenhum | nenhum | nenhum | nenhum |
| Guardião | 1ª vitória | 30–50 | 3–5 | 1,5% de 1 | até 2 diferentes; slots 70% e 25% |
| Guardião | 2ª vitória | 8–15 | 1 | nenhum | até 1 comum; slot 35% |
| Guardião | 3ª vitória | 2–5 | nenhum | nenhum | nenhum |
| Guardião | 4ª e seguintes | nenhum | nenhum | nenhum | nenhum |

Cobre e prata são garantidos nas etapas 1 e 2; na terceira, apenas cobre. As verificações de cada slot são independentes; ambos podem falhar, deixando somente moedas. Slot aprovado usa sorteio ponderado entre itens elegíveis, excluindo o item já escolhido. Pesos abaixo **não são chances finais individuais**. Etapa 2 filtra somente Comum, retirando raros e documentos especiais. Quantidades são sorteadas no intervalo indicado.

| Fonte | ID | Runtime | Raridade | Peso | Quantidade |
|---|---|---|---|---|---|
| Baú | ITEM-026 | racao_explorador | Comum | 30 | 1–2 |
| Baú | ITEM-027 | bandagem_campo | Comum | 25 | 1–2 |
| Baú | ITEM-029 | taca_bronze_antiga | Comum | 20 | 1 |
| Baú | ITEM-032 | frasco_oleo_lamparina | Comum | 15 | 1–2 |
| Baú | ITEM-030 | relicario_pedra | Raro | 6 | 1 |
| Baú | ITEM-031 | fragmento_registro_antigo | Raro | 4 | 1 |
| Guardião | ITEM-033 | elmo_cobre | Comum | 40 | 1 |
| Guardião | ITEM-034 | peitoral_couro | Comum | 40 | 1 |
| Guardião | ITEM-035 | escudo_ferro_reforcado | Raro | 8 | 1 |
| Guardião | ITEM-036 | candelabro_expedicao | Raro | 7 | 1 |
| Guardião | ITEM-037 | pernil_assado | Raro | 5 | 1 |

ITEM-028 (`bolsa_moedas_antigas`) possui cadastro informativo, mas representa **crédito direto**: as moedas selecionadas entram na carteira existente, sem entregar um segundo recipiente. Conversão preservada: 10 cobres = 1 prata; 100 pratas = 1 ouro, portanto 1 ouro = 1.000 cobres. Não existe uma segunda carteira.

Toda a tabela de recompensa e seus pesos estão em `ServerScriptService.PISO1_RecompensasConfig`. Novos cadastros futuros podem ampliar suas categorias; nesta versão somente Piso 1 é autorizado.

## Inventário, usos e informação

Os novos cadastros têm identificação, raridade, origem, descrição curta/detalhada, propriedades, usos atuais/futuros e miniaturas na inspeção, alforge e ficha independente. A interface distingue recompensa individual de espólios compartilhados. Inventário admite até 99 unidades por cadastro novo, provisoriamente. Seleção que ultrapasse capacidade não altera carteira, estoque nem recibo; o jogador pode selecionar uma quantidade menor.

Ração cura 25%, Bandagem 15% e Pernil 100% da vida máxima, limitados ao máximo. USAR consome uma unidade por transação persistente e aplica a cura após confirmação. Não foi adicionada cura de veneno. Os consumíveis antigos da Padaria permanecem no caminho existente.

LER REGISTRO exige possuir o Fragmento, registra `RegistroGuerreiroEsquecido` na seção persistente do Diário e mostra `DIARIO-CAP1-005`. Texto fixo preservado de DOS-005. O papel não é consumido; a descoberta permanece após remoção ou futura venda. Não cria missão, localização do elmo ou atendimento de investigação em Cedric.

Óleo permanece sem abastecimento funcional. Elmo de Bronze, peitoral e escudo foram integrados posteriormente ao equipamento existente; candelabro possui lançamento direto pela bolsa, iluminação, coleta e desgaste. Estado detalhado em ITEM-033–036. Elmo reduz provisoriamente 5% do dano de combate; defesa numérica do peitoral e superioridade do escudo ainda não definidas. Reparos, sucata e abastecimento continuam futuros. Taça/Relicário e os novos equipamentos não receberam preços de venda; catálogo atual da Guilda continua ITEM-008–022.

As imagens tituladas 1672 × 941 da Parte 1 permanecem intactas no GDD. A gameplay usa miniaturas procedurais nativas da interface existente: 12 desenhos conferidos, sem importação das PNGs como assets Roblox. Aprovação artística final permanece pendente.

## Persistência e segurança

Extensão do perfil existente `BP_DataStore_V1`: na implantação desta etapa, o template versão 4 reconciliou dados antigos, adicionando `RecompensasMasmorra` e `Diario.Descobertas`. Reutiliza `PersistenciaService`, inventário e carteira, preservando dados de Guilda e demais sistemas.

O servidor calcula a data por UTC menos 3 horas e renova os contadores à meia-noite de Brasília, na próxima operação da categoria. Reconectar, trocar de servidor, reconstruir a masmorra ou resetar progresso não renova artificialmente o limite. Cada geração e encontro possui GUID estável; resultado, etapa, saldo remanescente e revisão ficam no perfil do jogador.

Sorteio ocorre no servidor. Revisão, quantidade inteira finita, pertencimento à lista, capacidade, distância, personagem vivo e participação são conferidos. O cliente não escolhe preços, moedas, categoria ou itens fora do resultado. Concessão de inventário, moedas, contador e recibo usa a mesma transação `UpdateAsync`, com bloqueio de sessão existente, token idempotente e recuperação em segundo plano diante de resposta perdida. Até confirmação, nova operação financeira fica bloqueada e nenhum crédito é antecipado.

Coleta parcial permanece recuperável após desmontagem ou reconexão: um encontro posterior da mesma categoria pode apresentar uma pendência já reservada. Recuperar espólios antigos não concede novos itens nem consome outra etapa diária. Recibos parcialmente recolhidos ou vitórias com itens pendentes não são descartados. Recibos concluídos e preparações não cobradas têm retenção de 30 dias; fontes físicas anteriores a esse prazo não geram uma nova recompensa. Isso impede renovar direitos antigos após a limpeza do histórico.

A reserva automática do Guardião tenta novamente quando o perfil está ocupado e pode ser retomada na inspeção se ainda não gravada. A chave e os controladores de saída não dependem dessa gravação. Falhas de serviço e concorrência foram simuladas; interrupção real do servidor no exato instante da morte continua um cenário de homologação.

## Scripts modificados

Novos módulos/controlador: `ServerScriptService.PISO1_RecompensasConfig`, `PISO1_RecompensasService` e `PISO1_RecompensasRuntime`.

Extensões existentes:

- `ReplicatedStorage.DadosItens.BancoDeItens`, `TemplateDados` e `InformacoesMoedas`.
- `ServerScriptService.SistemasGameplay.PersistenciaService` e `GerenciadorComercioServer`.
- `ServerScriptService.EspoliosService` e `StarterPlayer.StarterPlayerScripts.EspoliosClient`.
- `ServerStorage.Dungeon_Baus.BauDeTesouro.ControladorBau`.
- `ServerStorage.Dungeon_NPCs.Golem_Pedra.NPCCombatController`: somente ligação ao acompanhamento de participação/recompensa, sem mudança de ataques.
- `ReplicatedStorage.DadosNarrativa.BancoDeDiario` e `ServerScriptService.SistemaDiario.GerenciadorDiarioServer`.
- `StarterGui.UI_Inventario_BatalhasPoderosas.MenuInventarioClient` e `ReplicatedStorage.BP_ItemInterface`.

Total: 16 scripts/módulos. Originais preservados em `ServerStorage.RECOMPENSAS_PISO1_PARTE2_BACKUP_20261011`; fontes antes/depois e resultados foram exportados. `InventarioService`, tabelas dos espólios comuns, geração procedural, chave, saídas e prefabs não foram substituídos. `index.html`, renderizador e arquitetura do site permanecem intactos.

## Testes efetivamente realizados

| Ambiente | Resultado e limite |
|---|---|
| Sintaxe Luau | 16 fontes compiladas sem erros; conferência final entre fontes locais e Studio. |
| Serviços reais com backend isolado de teste | 18 cenários passaram: primeira/segunda/terceira/quarta etapa; dois jogadores simulados no mesmo baú; repetição; nova geração; Guardião independente e vitória sem coleta; seleção parcial/capacidade inválida; leitura; reset; nova sessão; virada UTC/Brasília; concorrência; falha antes da gravação; resposta perdida após commit; entrega/pagamento único na Guilda. |
| Distribuição | 20.000 resultados de Baú/Guardião conferidos: limites, raridades, exclusões e itens distintos. |
| DataStore real isolado | `BP_Recompensas_Testes_20261011`: gravação, recarga do perfil, manutenção do saldo/contador e recusa de segunda coleta do mesmo baú. Sem conceder itens ou moedas de teste ao perfil de John. |
| Play com John | Portal gerou a masmorra; janela do Baú abriu individual, reabrir manteve resultado e não gastou etapa; cadáver do Guardião exibiu moedas e Peitoral de Couro; não participante foi recusado. Reserva de vitória confirmada antes da inspeção; perfil restaurado após esse teste controlado. |
| Chave e progressão em Play | Chave disponível após derrota, coletada e consumida no mecanismo existente; portal liberado. |
| Curas com handler existente e perfil isolado | 40/100 HP → 65, 55 e 100 para Ração, Bandagem e Pernil; estoque 1 → 0; segunda utilização recusada. Sem alterar o inventário real de John. |
| Miniaturas no cliente | 12 desenhos nativos criados com geometria própria, sem fallback; layout de inspeção observado no cliente. |
| Espólios anteriores | 100 sorteios por espécie para Vesplume, Grumelo, Pedrino, Brisalto, Cascudo e Baú Falso; IDs e quantidades válidos. Configuração comum preservada. Não substitui teste completo de coleta dos seis em multiplayer. |

**Pendente:** dois clientes reais coletando simultaneamente, desconexão/troca real entre servidores durante uma transação, virada real de meia-noite, inventário cheio e erros reais de DataStore no cliente, passagem completa com grupo, revisão artística e teste completo da Padaria/Guilda com atendimento físico. Os testes de concorrência, reconexão, falha e relógio acima usam simulação controlada, além da recarga em DataStore real. Não são homologação multiplayer. Não foi publicada uma nova versão do place nesta etapa.

## Correção de interação após teste do usuário — 11/10/2026

O baú verdadeiro estava ativo, mas seu botão não aparecia: o supressor global usa estilo Custom e EspoliosClient reconhecia apenas o prompt dos corpos. A interface agora reconhece também `PromptBau` do Baú Verdadeiro do Piso 1. Teste pelo acionamento nativo do prompt confirmou ABRIR, abertura da tampa e janela individual com itens/moedas em uma nova sessão de Play. Nenhuma recompensa foi coletada pelo agente. A validação anterior pelo atalho de teste do controlador não havia coberto essa apresentação do botão; este teste cobre o fluxo de interação.

## Próxima avaliação

Testar com John e outros jogadores, especialmente direitos individuais, coleta parcial, três rendimentos, quarta interação vazia e progressão pela chave. Refinar valores e arte depois da avaliação. Equipamentos funcionais foram autorizados e integrados posteriormente (ITEM-033–036); missões de investigação, manutenção e venda dos novos itens continuam futuras. A versão 5 do mesmo perfil acrescentou marcadores narrativos (GAME-014), preservando RecompensasMasmorra.

## Evidências das integrações posteriores

Elmo: equipar/desequipar e status 5% de redução/95% de dano recebido conferidos localmente, com ocultação/restauração de cabelo. Peitoral: testes de idle, caminhada, ataque, guarda, repetição e posse; nenhum bônus defensivo numérico aprovado. Escudo: prefab físico integrado ao slot secundário e regras existentes; balanceamento específico pendente. Candelabro: Play com três lançamentos/coletas, luz, bloqueio do quarto uso e preservação do item danificado; revisão final testou clique LANCAR, fechamento da bolsa, retorno da espada e coleta E. Não houve homologação multiplayer ou em dispositivo físico dessas integrações nesta documentação.
