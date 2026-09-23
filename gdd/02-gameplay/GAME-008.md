---
id: "GAME-008"
nome: "Mapa de Integração do Mundo de Arkham"
funcao: "Plano Mestre de Consolidação, NPCs, Economia e Gameplay"
status: "EM_DESENVOLVIMENTO"
localizacao: "Vila de Arkham & Fazenda de Arkan"
relacionados:
  - "GAME-001"
  - "GAME-004"
  - "GAME-006"
  - "GAME-007"
  - "LOCAL-001"
  - "LOCAL-002"
  - "LOCAL-003"
  - "LOCAL-004"
  - "LOCAL-005"
  - "LOCAL-006"
  - "LOCAL-007"
  - "LOCAL-008"
  - "LOCAL-009"
  - "NPC-001"
  - "NPC-002"
  - "NPC-003"
  - "NPC-004"
  - "NPC-005"
  - "NPC-006"
  - "NPC-007"
  - "NPC-008"
  - "NPC-009"
  - "NPC-010"
  - "NPC-011"
  - "NPC-012"
  - "NPC-013"
  - "NPC-014"
  - "NPC-015"
  - "NPC-016"
  - "NPC-017"
atualizado_por: "ChatGPT"
data_atualizacao: "2026-09-23"
---

# Mapa de Integração do Mundo de Arkham

> Documento operacional para encerrar a fase de construção dispersa e conduzir Arkham por uma linha de integração verificável.  
> **Regra central:** uma nova construção só entra na fila quando fechar uma necessidade real de NPC, profissão, cadeia produtiva, missão, serviço ou progressão.

## 1. Objetivo

Transformar o conjunto já construído de Arkham e da Fazenda de Arkan em uma rede jogável conectada:

```
LOCAL ↔ NPC ↔ PROFISSÃO ↔ RECURSO/PRODUTO ↔ ATIVIDADE ↔ RECOMPENSA ↔ CONSUMO/PROGRESSÃO
```

Este documento não fixa preços, moeda, drops de masmorra ou missões ainda não aprovadas. Exemplos discutidos durante o planejamento permanecem exemplos até serem formalizados em documento próprio.

## 2. Legenda de acompanhamento

- ✅ **CONCLUÍDO** — marco executado e validado.
- 🔄 **RECORRENTE** — processo-base já estabelecido, mas que deve ser revisitado continuamente ao longo do desenvolvimento.
- 🔁 **SOB DEMANDA** — marco-base concluído; reabre quando uma mudança, divergência ou nova implementação exigir nova validação.
- 🟡 **EM ANDAMENTO / PARCIAL** — etapa atualmente trabalhada ou existente, mas ainda incompleta.
- ⬜ **PENDENTE** — precisa ser criado, definido ou implementado.
- 🔎 **AUDITAR** — precisa ser conferido diretamente no Workspace antes de qualquer decisão.
- ⛔ **BLOQUEADO** — depende de etapa anterior.

> **Regra de leitura:** uma etapa pode estar concluída como marco histórico e, ao mesmo tempo, permanecer recorrente ou sob demanda. Isso não reabre o marco automaticamente; indica apenas que seu mecanismo de controle continua ativo.

## 3. Matriz atual: NPC ↔ local ↔ função

| NPC | Profissão / papel | Local relacionado | Estado | Próxima ação |
|---|---|---|---|---|
| Mestre Cedric | Ferreiro | Oficina do Cedric (LOCAL-002) | ✅ | Assentado e validado no posto; ampliar serviços somente em etapa própria |
| Ancião Eldrin | Guardião da Floresta | Árvore Sagrada (LOCAL-004) | ✅ | Assentado e validado no Santuário; rotina profissional futura |
| Guarda Rowan | Sentinela | Posto dos Acessos Leste | ✅ | Assentado; rota anterior preservada e pausada de forma reversível |
| Guarda Aldous | Sentinela | Praça Central (LOCAL-003) | ✅ | Restaurado como `Base_Guarda_Aldous`, assentado e validado; rota preservada e pausada individualmente |
| Padeira Beatrice | Padeira | Padaria (LOCAL-005) | ✅ | Assentada próxima ao balcão; rotina profissional futura |
| Pescador Lucan | Pescador | Cais (LOCAL-006) | ✅ | Assentado no Cais; cadeia econômica do pescado ainda pendente |
| Mercador Tobias | Mercador de provisões | Armazém da Vila | ✅ | Modelo legado confirmado como o próprio Tobias, recuperado como `NPC_Mercador_Tobias`, assentado e validado; migração R6 → R15 permanece débito técnico futuro |
| Agricultor Hugo | Agricultor / logística rural | Pátio de Carga da Fazenda (LOCAL-009) | ✅ | Recuperado, assentado sem rota ativa e validado em Playtest; diálogo funcional |
| Guardião Seraphin | Guardião do Portal | Portal (LOCAL-008) | ✅ | Assentado no acesso ao Portal sem bloquear a passagem |
| Lenhador Garrick | Lenhador | Serraria / Floresta Nordeste | ✅ | Assentado na Serraria Hidráulica; ficha LOCAL própria ainda pode ser avaliada |
| Mineiro Borin | Mineiro | Minas (LOCAL-007) | ✅ | Assentado na entrada da Mina; cadeia minério → destino ainda pendente |
| Kellan | Mineiro | Entrada Leste da Vila / acesso ao caminho da Mina (LOCAL-007) | ✅ | Assentado no ponto técnico `Guarda_PortaLeste`; `RotaMineiroB` preservada e pausada; Playtest validado |
| Agricultora Nalia | Agricultura / animais | Fazenda (LOCAL-009) | ✅ | Assentada na Horta da Fazenda; rotina operacional futura |
| Fazendeiro Geraldo | Administrador | Casa do Fazendeiro / Fazenda | ✅ | Assentado na Administração da Fazenda; rotina administrativa futura |

**Rei Mago (NPC-000):** fora da malha econômica cotidiana da vila; não entra na etapa de posicionamento profissional de Arkham.

## 4. Lacunas já detectadas documentalmente

- ✅ **Armazém do Mercador Tobias:** construção física e posto confirmados; Tobias recuperado e assentado. A necessidade de ficha LOCAL própria pode ser avaliada documentalmente sem bloquear a Etapa 3.
- 🟡 **Serraria de Garrick:** profissão e área existem; confirmar construção física e necessidade de LOCAL próprio.
- 🟡 **Pescado de Lucan:** origem definida; destino econômico ainda precisa ser fechado.
- 🟡 **Mineração de Borin:** origem definida; cadeia de uso/comércio precisa ser fechada.
- 🟡 **Lã:** GAME-006 prevê mantos, estofados e vestimentas; responsável comercial/artesanal ainda não está definido.
- ⬜ **Pastor de Arkan:** GAME-006 registra responsável futuro para o setor de ovelhas.
- 🟡 **Alfaiataria / oficina de vestimentas:** citada como destino produtivo no GAME-006, mas sem NPC/local próprio confirmado.
- 🔎 **Guilda e atendente:** auditar Workspace e documentação antes de formalizar; função econômica futura discutida, ainda não canonizada neste documento.
- 🔎 **Taverna:** auditar presença e estado físico no Workspace e cruzar com documentação.
- 🔎 **Silo:** necessidade levantada durante planejamento, mas só deve ser aprovado após auditoria logística da Fazenda.
- ⬜ **Catálogo econômico completo:** produtos, consumíveis, armas, armaduras, roupas/skins, ferramentas, matérias-primas e serviços.
- ⬜ **Moeda e preços:** bloqueados até conclusão do catálogo econômico e das cadeias de produção/consumo.

## 5. Checklist mestre por etapa

### ETAPA 1 — Auditoria documental

> ✅ **CONCLUÍDA COMO BASE | 🔄 RECORRENTE.** A auditoria documental inicial foi executada e consolidada. A partir deste marco, ela permanece como processo permanente de manutenção: toda alteração documental relevante deve revalidar referências, estados e coerência do GDD. Isso não significa que a etapa esteja pendente ou reaberta continuamente.

- [x] Registrar o levantamento documental inicial de NPCs, locais, itens e Fazenda.
- [x] Identificar as primeiras lacunas de catálogo e referências.
- [~] Revalidar referências e estados após cada alteração documental relevante.
- [x] Separar as afirmações que exigiam validação física e encaminhá-las para a auditoria do Workspace.
- [~] Manter a auditoria documental ativa de forma recorrente sempre que documentos relevantes forem criados ou alterados.

**Saída da etapa:** inventário documental rastreável, com incertezas explícitas e itens separados para validação no Studio.

### Resultado consolidado da auditoria documental

**Recursos/produtos já documentados:** Madeira Comum, Madeira Sagrada, Espada de Madeira Sagrada, trigo, milho, vegetais, cultivos variados, frutas/pomar, produtos da horta, farinha, grãos, rações, feno, ovos, lã, leite, pescados, minérios e materiais subterrâneos, além de tesouros/recompensas de masmorra já citados em DNG-001/002.

**Serviços/funções documentados:** forja e aprimoramento com Cedric; comércio/provisões e avaliação de relíquias atribuídos a Tobias; panificação com Beatrice; pesca com Lucan; agricultura e logística rural com Hugo/Nalia/Geraldo; madeira/serraria com Garrick; mineração com Borin; patrulha/segurança com Rowan/Aldous; guarda do portal com Seraphin. A existência física e o nível de integração desses serviços devem ser validados no Studio.

**Gameplay já conectado:** coleta inicial, forja, combate, diálogo, Diário, navegação, colheita/carregamento planejados, masmorra procedural, baús, minérios, Chave do Guardião e retorno à vila.

### Inconsistências e pontos que a Etapa 2 deve confirmar

- ✅ A referência de `GAME-006` que tratava `LOCAL-003` como Armazém Central foi corrigida nesta auditoria. Tobias permanece associado ao Armazém da Vila, ainda sem `LOCAL` próprio confirmado.
- 🔎 Garrick possui Serraria & Floresta Nordeste em sua ficha, sem LOCAL próprio.
- ✅ Kellan (`NPC-017`) foi identificado como Mineiro, assentado na Entrada Leste da Vila no acesso ao caminho da Mina e documentado; Borin permanece distinto na entrada da Mina.
- ✅ Armand (`NPC-015`) e Leofric (`NPC-016`) foram confirmados fisicamente como guardas R15 fixos no pórtico da entrada da masmorra, validados em Playtest e documentados em fichas próprias.
- 🔎 `DNG-002` já documenta comércio subterrâneo com Tobias, Ouro Arcaico, poções/tônicos/kits, taxa de Guilda e materiais de forja. Isso precisa ser confrontado com o que realmente está implementado antes de ampliar ou balancear a economia.
- 🔎 `DNG-001` afirma que a masmorra é a única fonte de recursos raros necessários ao fortalecimento do reino, enquanto o plano de integração exige múltiplas fontes de renda e atividade. Na próxima revisão de design, separar claramente **recursos raros de aventura** de **fontes gerais de renda**.
- 🔎 `GAME-002` documenta combo atual de 5 golpes; qualquer divergência com o comportamento real do John deve ser verificada no Studio.
- 🔎 Defesa aparece visualmente preparada em `GAME-003`, mas ainda não implementada.
- 🔎 `DNG-006` registra validação pendente da coleta corrigida da Chave do Guardião.
- ✅ O prefab `ServerStorage.Dungeon_NPCs.Automato_Lacaio` foi limpo dos dados indevidos de Rowan; a origem era o próprio prefab salvo, sem script reaplicando a contaminação. Clonagem/controlador foram validados em Playtest controlado; a geração procedural completa permanece para validação futura.
- 🟡 Pastor, alfaiataria e destinos finais de lã/pescado/madeira continuam lacunas documentais deliberadas, a serem decididas após a auditoria física.

**Decisão operacional:** nenhuma dessas inconsistências será corrigida por suposição. Elas entram como alvos objetivos da auditoria do Workspace.

### ETAPA 2 — Auditoria física do Workspace

> ✅ **CONCLUÍDA COMO BASE EM 22/09/2026 | 🔁 SOB DEMANDA.** Auditoria geral executada em Edit mode, sem alterações durante a inspeção. A base física mostrou-se mais completa que a documentação. Esta etapa só deve ser reaberta quando mudanças físicas relevantes, divergências GDD ↔ Studio ou dúvidas de implementação exigirem nova conferência.

- [x] Inspecionar a Vila de Arkham sem modificar nada.
- [x] Listar construções físicas, estabelecimentos e interiores relevantes.
- [x] Listar NPCs presentes e posições encontradas.
- [x] Identificar objetos funcionais e pontos de interação existentes.
- [x] Conferir a Fazenda e suas 26 áreas contra LOCAL-009.
- [x] Confirmar estruturas físicas de comércio, serraria, taverna e outros estabelecimentos ainda sem ficha LOCAL própria.
- [x] Registrar divergências GDD ↔ Workspace.
- [x] Separar presença física de funcionalidade comprovada: prompts/estruturas encontrados não significam, por si só, cadeia econômica implementada.

**Saída da etapa:** auditoria física concluída. Permanecem validações de runtime específicas para sistemas que exigem Playtest.

### ETAPA 3 — Casamento NPC ↔ estabelecimento

> 🟡 **PARCIAL AVANÇADA EM 23/09/2026.** O núcleo dos profissionais documentados foi consolidado: Aldous, Tobias e Hugo foram resolvidos e validados, somando-se aos dez profissionais anteriormente assentados. A pendência principal passa a ser a regularização dos NPCs físicos ainda sem correspondência documental suficiente.

- [x] Assentar Mestre Cedric na Oficina/Forja.
- [x] Assentar Ancião Eldrin no Santuário/Árvore Sagrada.
- [x] Assentar Rowan no Posto dos Acessos Leste.
- [x] Assentar Beatrice na Padaria.
- [x] Assentar Lucan no Cais.
- [x] Assentar Garrick na Serraria Hidráulica.
- [x] Assentar Borin na entrada da Mina.
- [x] Assentar Nalia na Horta da Fazenda.
- [x] Assentar Geraldo na Administração da Fazenda.
- [x] Assentar Seraphin no acesso ao Portal Mundo Livre sem bloquear a passagem.
- [x] Preservar as rotas anteriores e permitir pausa individual reversível para profissionais assentados.
- [x] Validar em Playtest que os profissionais assentados permanecem no posto e que civis continuam circulando.
- [x] Resolver Tobias: modelo legado identificado como o próprio mercador, recuperado e assentado no Armazém; estado anterior preservado para reversão e Playtest validado.
- [x] Restaurar e assentar Aldous na Praça Central, mantendo Maelis distinta; rota preservada/pausada individualmente e Playtest validado.
- [x] Recuperar e assentar Hugo no Pátio de Carga da Fazenda, sem rota ativa; diálogo e permanência no posto validados.
- [x] Regularizar documentalmente Armand e Leofric após validação física no pórtico da masmorra.
- [x] Regularizar Kellan como Mineiro da Entrada Leste, preservando `RotaMineiroB` como estado anterior e validando seu posto em Playtest.
- [ ] Resolver documentalmente Maelis e demais NPCs físicos ainda sem correspondência suficiente.
- [ ] Criar novos NPCs somente para lacunas aprovadas.
- [ ] Criar fichas LOCAL adicionais somente para construções confirmadas que realmente precisem de documentação própria.
- [ ] Projetar rotinas profissionais contextuais somente depois do assentamento e das funções estarem consolidados.

**Critério de conclusão:** cada estabelecimento funcional possui responsável confirmado ou justificativa explícita para não possuir, sem inventar correspondências.

### ETAPA 4 — Mapa de necessidades, utilidades e progressão

> ⬜ **NOVA ETAPA DE DESIGN.** Antes de multiplicar itens ou transformar cadeias em gameplay, definir por que cada família de recurso existe, qual problema resolve e quais escolhas oferece ao jogador.

Modelo de análise:

```
DESAFIO / NECESSIDADE
        ↓
SOLUÇÕES POSSÍVEIS
        ↓
ITEM / RECURSO
        ↓
FORMAS DE OBTENÇÃO
(compra, coleta, produção, exploração, recompensa...)
        ↓
TRANSFORMAÇÃO / COMBINAÇÃO
        ↓
NPC / LOCAL RELACIONADO
        ↓
USO
        ↓
XP / PROGRESSÃO / NOVAS POSSIBILIDADES
```

Princípios desta etapa:

- [ ] Nenhum item entra apenas porque “é comum em RPG”; cada família precisa de utilidade identificável.
- [ ] Sempre que fizer sentido, oferecer mais de um caminho de obtenção: comprar, coletar, produzir, combinar, explorar ou receber como recompensa.
- [ ] Fazer crafting/combinação funcionar como alternativa e escolha, não como obrigação artificial.
- [ ] Definir necessidades da aventura antes de criar consumíveis para resolvê-las.
- [ ] Avaliar cura, preparação para expedições, efeitos de estado, alimentação, vigor/estamina e outros sistemas antes de canonizá-los.
- [ ] Não criar fome, estamina ou outra barra apenas para justificar itens; primeiro definir seu papel real no gameplay.
- [ ] Relacionar atividades praticadas a possíveis formas de experiência/progressão sem descaracterizar a identidade principal de John.
- [ ] Avaliar progressões secundárias por prática, como competências de coleta, produção ou formas limitadas de combate, antes de transformá-las em sistema canônico.
- [ ] Usar a masmorra como fonte possível de necessidades de preparação e recursos de aventura, sem torná-la a única origem de renda ou progressão.
- [ ] Distinguir claramente **IDEIA**, **APROVADO**, **DOCUMENTADO**, **IMPLEMENTADO** e **VALIDADO NO STUDIO**.

**Exemplos discutidos, ainda NÃO canônicos:** poções de cura, antídotos, efeitos de veneno em pisos futuros, alimentos ligados a preparação/recuperação, estamina/vigor e competências secundárias de combate à distância. Estes exemplos servem para orientar o método e só viram conteúdo do jogo após decisão específica.

**Critério de conclusão:** as principais famílias de necessidade/recurso possuem propósito, alternativas de obtenção, destino e relação de progressão suficientemente claros para alimentar o catálogo econômico sem criar itens órfãos.

### ETAPA 5 — Catálogo econômico
- [ ] Catalogar matérias-primas.
- [ ] Catalogar produtos agrícolas.
- [ ] Catalogar produtos animais.
- [ ] Catalogar alimentos e consumíveis.
- [ ] Catalogar pescados.
- [ ] Catalogar madeira e derivados.
- [ ] Catalogar minérios e derivados.
- [ ] Catalogar armas.
- [ ] Catalogar armaduras e equipamentos.
- [ ] Catalogar ferramentas.
- [ ] Catalogar roupas, skins e cosméticos.
- [ ] Catalogar serviços: forja, melhoria, reparo, hospedagem, aluguel etc.
- [ ] Catalogar recursos de masmorra somente após aprovação de seus drops.
- [ ] Para cada entrada registrar: origem, produtor, comprador, consumidor, transformação e utilidade.

**Critério de conclusão:** nenhum preço é criado antes desta etapa estar suficientemente consolidada.

### ETAPA 6 — Teia de produção e logística
- [ ] Fechar trigo → moinho → farinha → Beatrice/padaria.
- [ ] Fechar Fazenda → armazenamento → carga → Tobias/vila.
- [ ] Fechar animais → produtos → destinos.
- [ ] Fechar lã → artesanato/vestuário.
- [ ] Fechar pesca → distribuição/consumo.
- [ ] Fechar madeira → serraria → produtos/destinos.
- [ ] Fechar mineração → processamento/comércio/forja.
- [ ] Definir onde carroças entram nas cadeias.
- [ ] Avaliar necessidade real de silo e outras construções faltantes.
- [ ] Só então autorizar novas construções funcionais.

### ETAPA 7 — Trabalhos, minijogos e missões econômicas
- [ ] Converter ligações adequadas da teia em atividades do jogador.
- [ ] Definir trabalhos repetíveis da Fazenda.
- [ ] Definir coleta, carga, transporte e entrega onde forem divertidos.
- [ ] Definir atividades de pesca/mineração/madeira quando aprovadas.
- [ ] Permitir que NPCs receptores abram novas oportunidades relacionadas.
- [ ] Separar missões econômicas opcionais da linha narrativa principal.
- [ ] Definir recompensas sem fixar valores prematuramente.

### ETAPA 8 — Guilda, masmorra e economia de aventura
- [ ] Confirmar papel e estrutura da Guilda.
- [ ] Definir NPC responsável pelo atendimento.
- [ ] Definir quais recursos de masmorra possuem valor fora da masmorra.
- [ ] Definir avaliação/entrega/recompensa.
- [ ] Conectar materiais de aventura a comércio, forja, progressão ou outros sistemas aprovados.
- [ ] Evitar que a masmorra seja a única fonte de renda.

### ETAPA 9 — Moeda, preços e balanceamento
- [ ] Definir moeda oficial.
- [ ] Criar cesta de referência de produtos cotidianos.
- [ ] Definir salários/recompensas de trabalhos.
- [ ] Definir compra e venda.
- [ ] Definir custos de equipamentos, consumíveis e serviços.
- [ ] Criar sumidouros de moeda.
- [ ] Balancear renda × progressão × tempo de jogo.
- [ ] Testar inflação e acúmulo excessivo.

### ETAPA 10 — Conteúdo, narrativa e vida cotidiana
- [ ] Preencher diálogos profissionais.
- [ ] Criar árvores de opções dos NPCs.
- [ ] Integrar informações, rumores e encaminhamentos entre NPCs.
- [ ] Criar horários/rotinas quando fizerem sentido.
- [ ] Integrar Diário/Livro quando uma atividade tiver peso narrativo.
- [ ] Garantir que a vila comunique suas funções pelo próprio comportamento dos habitantes.

## 6. Timeline operacional

```
FASE A  DOCUMENTAR
   ↓
FASE B  AUDITAR WORKSPACE
   ↓
FASE C  POSICIONAR NPCs E FECHAR ESTABELECIMENTOS
   ↓
FASE D  MAPEAR NECESSIDADES / UTILIDADES / ESCOLHAS DE PROGRESSÃO
   ↓
FASE E  CATALOGAR PRODUTOS / RECURSOS / SERVIÇOS
   ↓
FASE F  FECHAR CADEIAS DE PRODUÇÃO E LOGÍSTICA
   ↓
FASE G  TRANSFORMAR CADEIAS EM GAMEPLAY
   ↓
FASE H  CONECTAR GUILDA / MASMORRA / AVENTURA
   ↓
FASE I  DEFINIR MOEDA, PREÇOS E BALANCEAMENTO
   ↓
FASE J  EXPANDIR DIÁLOGOS, NARRATIVA E ROTINAS
```

As fases são dependências de trabalho, não datas. Atividades podem avançar em paralelo apenas quando não exigirem uma definição ainda pendente.

## 7. Regra de construção daqui em diante

Antes de construir qualquer novo prédio, responder:

1. Qual lacuna ele fecha?
2. Qual NPC ou profissão o utiliza?
3. O que entra nele?
4. O que sai dele?
5. O jogador faz o quê ali?
6. Com qual outro nó da vila ele se conecta?

Se essas respostas não existirem, a construção permanece em espera.

## 8. Próximo marco

**Marco imediato:** investigar e regularizar Maelis, seguida pelos demais NPCs físicos ainda sem correspondência suficiente, e então concluir a ETAPA 3 antes de iniciar a ETAPA 4, mapeando necessidades, utilidades e escolhas de progressão antes de expandir o catálogo econômico.

A auditoria física já foi concluída e o primeiro assentamento dos profissionais confirmados já foi validado. A partir daqui, novas decisões devem fechar lacunas verificáveis em vez de espalhar sistemas desconectados.

A fundação de Menu/Inventário está em processo de atualização no Studio para receber os sistemas futuros; ela não deve ser marcada como concluída até a validação final da implementação.

Este documento deve ser atualizado continuamente: cada pendência concluída muda para ✅, permitindo que o desenvolvimento avance por fechamento de lacunas em vez de expansão aleatória.
