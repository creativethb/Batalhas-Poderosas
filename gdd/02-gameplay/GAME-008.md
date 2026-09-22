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
atualizado_por: "ChatGPT"
data_atualizacao: "2026-09-22"
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

- ✅ **FEITO** — documentado e já casado no GDD.
- 🟡 **PARCIAL** — existe, mas falta integração, confirmação física ou conteúdo.
- ⬜ **PENDENTE** — precisa ser criado, definido ou implementado.
- 🔎 **AUDITAR** — precisa ser conferido diretamente no Workspace antes de qualquer decisão.
- ⛔ **BLOQUEADO** — depende de etapa anterior.

## 3. Matriz atual: NPC ↔ local ↔ função

| NPC | Profissão / papel | Local relacionado | Estado | Próxima ação |
|---|---|---|---|---|
| Mestre Cedric | Ferreiro | Oficina do Cedric (LOCAL-002) | ✅ | Posicionar/validar posto real no Workspace e depois ampliar serviços |
| Ancião Eldrin | Guardião da Floresta | Árvore Sagrada (LOCAL-004) | ✅ | Validar posição e rotina |
| Guarda Rowan | Sentinela | Praça / acesso leste / mina | ✅ | Validar rota territorial |
| Guarda Aldous | Sentinela | Praça Central (LOCAL-003) | ✅ | Validar rota territorial |
| Padeira Beatrice | Padeira | Padaria (LOCAL-005) | ✅ | Posicionar/validar balcão, forno e banca |
| Pescador Lucan | Pescador | Cais (LOCAL-006) | ✅ | Posicionar/validar cais e definir cadeia econômica do pescado |
| Mercador Tobias | Mercador de provisões | Armazém da Vila | 🟡 | 🔎 Confirmar prédio no Workspace e criar ficha LOCAL se necessário |
| Agricultor Hugo | Agricultor | Colina / Fazenda | 🟡 | Definir posto definitivo após auditoria |
| Guardião Seraphin | Guardião do Portal | Portal (LOCAL-008) | ✅ | Validar posto real |
| Lenhador Garrick | Lenhador | Serraria / Floresta Nordeste | 🟡 | 🔎 Confirmar serraria no Workspace e criar ficha LOCAL se necessário |
| Mineiro Borin | Mineiro | Minas (LOCAL-007) | ✅ | Validar posto e cadeia minério → destino |
| Agricultora Nalia | Agricultura / animais | Fazenda (LOCAL-009) | ✅ | Fixar setor/rotina operacional |
| Fazendeiro Geraldo | Administrador | Casa do Fazendeiro / Fazenda | ✅ | Fixar rotina administrativa e pontos de trabalho |

**Rei Mago (NPC-000):** fora da malha econômica cotidiana da vila; não entra na etapa de posicionamento profissional de Arkham.

## 4. Lacunas já detectadas documentalmente

- 🟡 **Armazém do Mercador Tobias:** NPC e função existem; confirmar construção física e necessidade de LOCAL próprio.
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

> 🔎 **Estado atual: REABERTA EM 22/09/2026.** A lista anterior foi um levantamento inicial. Alterações posteriores — incluindo o dossiê de John (`NPC-014`) e esta revisão de referências, economia e masmorra — exigem manutenção contínua. Esta etapa não confirma a existência física nem a implementação de runtime.

- [x] Registrar o levantamento documental inicial de NPCs, locais, itens e Fazenda.
- [x] Identificar as primeiras lacunas de catálogo e referências.
- [~] Revalidar referências e estados após cada alteração documental relevante.
- [ ] Confrontar afirmações de implementação com o Roblox Studio, sem alterar o Workspace durante a auditoria documental.

**Saída da etapa:** inventário documental rastreável, com incertezas explícitas e itens separados para validação no Studio.

### Resultado consolidado da auditoria documental

**Recursos/produtos já documentados:** Madeira Comum, Madeira Sagrada, Espada de Madeira Sagrada, trigo, milho, vegetais, cultivos variados, frutas/pomar, produtos da horta, farinha, grãos, rações, feno, ovos, lã, leite, pescados, minérios e materiais subterrâneos, além de tesouros/recompensas de masmorra já citados em DNG-001/002.

**Serviços/funções documentados:** forja e aprimoramento com Cedric; comércio/provisões e avaliação de relíquias atribuídos a Tobias; panificação com Beatrice; pesca com Lucan; agricultura e logística rural com Hugo/Nalia/Geraldo; madeira/serraria com Garrick; mineração com Borin; patrulha/segurança com Rowan/Aldous; guarda do portal com Seraphin. A existência física e o nível de integração desses serviços devem ser validados no Studio.

**Gameplay já conectado:** coleta inicial, forja, combate, diálogo, Diário, navegação, colheita/carregamento planejados, masmorra procedural, baús, minérios, Chave do Guardião e retorno à vila.

### Inconsistências e pontos que a Etapa 2 deve confirmar

- ✅ A referência de `GAME-006` que tratava `LOCAL-003` como Armazém Central foi corrigida nesta auditoria. Tobias permanece associado ao Armazém da Vila, ainda sem `LOCAL` próprio confirmado.
- 🔎 Garrick possui Serraria & Floresta Nordeste em sua ficha, sem LOCAL próprio.
- 🔎 `LOCAL-007` menciona Mineiro Kellan, mas não existe ficha NPC correspondente no catálogo atual.
- 🔎 `GAME-002` registra Armand e Leofric na entrada da masmorra, porém eles não possuem fichas NPC no catálogo atual.
- 🔎 `DNG-002` já documenta comércio subterrâneo com Tobias, Ouro Arcaico, poções/tônicos/kits, taxa de Guilda e materiais de forja. Isso precisa ser confrontado com o que realmente está implementado antes de ampliar ou balancear a economia.
- 🔎 `DNG-001` afirma que a masmorra é a única fonte de recursos raros necessários ao fortalecimento do reino, enquanto o plano de integração exige múltiplas fontes de renda e atividade. Na próxima revisão de design, separar claramente **recursos raros de aventura** de **fontes gerais de renda**.
- 🔎 `GAME-002` documenta combo atual de 5 golpes; qualquer divergência com o comportamento real do John deve ser verificada no Studio.
- 🔎 Defesa aparece visualmente preparada em `GAME-003`, mas ainda não implementada.
- 🔎 `DNG-006` registra validação pendente da coleta corrigida da Chave do Guardião.
- 🟡 Pastor, alfaiataria e destinos finais de lã/pescado/madeira continuam lacunas documentais deliberadas, a serem decididas após a auditoria física.

**Decisão operacional:** nenhuma dessas inconsistências será corrigida por suposição. Elas entram como alvos objetivos da auditoria do Workspace.

### ETAPA 2 — Auditoria física do Workspace
- [ ] Inspecionar a Vila de Arkham sem modificar nada.
- [ ] Listar todas as construções físicas existentes.
- [ ] Listar interiores e estabelecimentos utilizáveis.
- [ ] Listar NPCs realmente presentes e posição atual.
- [ ] Listar objetos funcionais relevantes: balcões, fornos, bancadas, carroças, depósitos, campos, ferramentas, pontos de coleta etc.
- [ ] Conferir Fazenda e suas 26 áreas contra LOCAL-009.
- [ ] Confirmar Armazém de Tobias.
- [ ] Confirmar Serraria de Garrick.
- [ ] Confirmar Taverna.
- [ ] Verificar se já existe estrutura equivalente a silo.
- [ ] Registrar divergências GDD ↔ Workspace.

**Saída da etapa:** relatório físico do jogo, sem alterações.

### ETAPA 3 — Casamento NPC ↔ estabelecimento
- [ ] Definir posto definitivo de cada NPC profissional.
- [ ] Reposicionar NPCs que já possuem estabelecimento confirmado.
- [ ] Ajustar rotas curtas de trabalho quando necessárias.
- [ ] Manter guardas em rotas territoriais, não presos a balcões.
- [ ] Identificar profissões sem NPC.
- [ ] Identificar estabelecimentos sem responsável.
- [ ] Criar novos NPCs somente para lacunas aprovadas.
- [ ] Criar novas fichas LOCAL somente para construções confirmadas/aprovadas.
- [ ] Atualizar GDD após cada casamento concluído.

**Critério de conclusão:** cada estabelecimento funcional possui responsável ou justificativa explícita para não possuir.

### ETAPA 4 — Catálogo econômico
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

### ETAPA 5 — Teia de produção e logística
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

### ETAPA 6 — Trabalhos, minijogos e missões econômicas
- [ ] Converter ligações adequadas da teia em atividades do jogador.
- [ ] Definir trabalhos repetíveis da Fazenda.
- [ ] Definir coleta, carga, transporte e entrega onde forem divertidos.
- [ ] Definir atividades de pesca/mineração/madeira quando aprovadas.
- [ ] Permitir que NPCs receptores abram novas oportunidades relacionadas.
- [ ] Separar missões econômicas opcionais da linha narrativa principal.
- [ ] Definir recompensas sem fixar valores prematuramente.

### ETAPA 7 — Guilda, masmorra e economia de aventura
- [ ] Confirmar papel e estrutura da Guilda.
- [ ] Definir NPC responsável pelo atendimento.
- [ ] Definir quais recursos de masmorra possuem valor fora da masmorra.
- [ ] Definir avaliação/entrega/recompensa.
- [ ] Conectar materiais de aventura a comércio, forja, progressão ou outros sistemas aprovados.
- [ ] Evitar que a masmorra seja a única fonte de renda.

### ETAPA 8 — Moeda, preços e balanceamento
- [ ] Definir moeda oficial.
- [ ] Criar cesta de referência de produtos cotidianos.
- [ ] Definir salários/recompensas de trabalhos.
- [ ] Definir compra e venda.
- [ ] Definir custos de equipamentos, consumíveis e serviços.
- [ ] Criar sumidouros de moeda.
- [ ] Balancear renda × progressão × tempo de jogo.
- [ ] Testar inflação e acúmulo excessivo.

### ETAPA 9 — Conteúdo, narrativa e vida cotidiana
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
FASE D  CATALOGAR PRODUTOS / RECURSOS / SERVIÇOS
   ↓
FASE E  FECHAR CADEIAS DE PRODUÇÃO E LOGÍSTICA
   ↓
FASE F  TRANSFORMAR CADEIAS EM GAMEPLAY
   ↓
FASE G  CONECTAR GUILDA / MASMORRA / AVENTURA
   ↓
FASE H  DEFINIR MOEDA, PREÇOS E BALANCEAMENTO
   ↓
FASE I  EXPANDIR DIÁLOGOS, NARRATIVA E ROTINAS
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

**Marco imediato:** concluir ETAPA 1 e executar ETAPA 2.

Somente depois da auditoria do Workspace deve ser produzida a lista definitiva de:
- NPCs a reposicionar;
- NPCs novos necessários;
- construções faltantes;
- estabelecimentos que precisam de ficha LOCAL;
- cadeias econômicas abertas;
- prioridades de implementação.

Este documento deve ser atualizado continuamente: cada pendência concluída muda para ✅, permitindo que o desenvolvimento avance por fechamento de lacunas em vez de expansão aleatória.
