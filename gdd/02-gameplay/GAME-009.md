---
id: "GAME-009"
nome: "Painel Linear de Consolidação — Itens, Interações e Cadeias"
funcao: "Checklist operacional para quitar conteúdo físico e coletável antes de novas expansões"
status: "EM_DESENVOLVIMENTO"
localizacao: "Vila de Arkham"
relacionados:
  - "GAME-001"
  - "GAME-002"
  - "GAME-008"
  - "ITEM-001"
  - "ITEM-002"
  - "ITEM-003"
  - "ITEM-004"
  - "LOCAL-002"
  - "LOCAL-005"
  - "LOCAL-006"
  - "LOCAL-007"
atualizado_por: "ChatGPT"
data_atualizacao: "2026-09-23"
---

# Painel Linear de Consolidação — Itens, Interações e Cadeias

> Este documento é a fila operacional da fase atual. O objetivo é **parar a expansão horizontal**, consolidar o que Arkham já pede e quitar uma pendência por vez até que os sistemas escolhidos estejam definidos, criados, implementados, testados e validados.
>
> **Fora do escopo desta fase:** Fazenda de Arkan e suas cadeias próprias. Quando uma cadeia da vila depender futuramente da Fazenda, registrar apenas a dependência sem desenvolver o conteúdo rural aqui.

## 1. Regra de escopo

Entram neste painel apenas elementos materiais de gameplay que precisam existir de fato:

1. **Itens de interação** — objetos com os quais o jogador interage e que iniciam, recebem ou concluem uma ação: baú, veio de minério, ponto de pesca, bancada funcional, estação de produção etc.
2. **Itens coletáveis** — objetos ou recursos que entram no inventário ou são recebidos pelo jogador: madeira, minério, erva, peixe, componentes, chaves etc.
3. **Componentes e materiais** — itens consumidos em fabricação, troca ou aprimoramento.
4. **Consumíveis** — itens usados pelo jogador e consumidos pelo sistema.
5. **Equipamentos** — armas, escudos, proteção corporal, ferramentas e outros itens equipáveis.

Objetos puramente decorativos não entram neste painel.

**Regra física:** se um item puder ser coletado, recebido, encontrado, entregue, gasto, combinado, fabricado, aprimorado ou aparecer visualmente como resultado de uma interação, ele deve possuir uma definição própria e espaço previsto para representação visual/3D.

## 2. Estados de consolidação

A fila usa os seguintes estados, em ordem:

`A DEFINIR → DEFINIDO → CRIADO → IMPLEMENTADO → TESTADO → VALIDADO`

- **A DEFINIR:** necessidade identificada, mas nome, função ou regra ainda não fechados.
- **DEFINIDO:** função de gameplay aprovada e documentada.
- **CRIADO:** representação física/visual produzida.
- **IMPLEMENTADO:** conectado ao sistema correspondente no jogo.
- **TESTADO:** passou por teste funcional.
- **VALIDADO:** aprovado como concluído para esta fase.

**Só VALIDADO quita uma pendência.**

## 3. Raridade e propriedade

### Raridades ativas nesta fase
- **Comum** — base da coleta, economia, fabricação e equipamento inicial.
- **Raro** — obtenção menos frequente, receitas melhores, exploração e aprimoramentos.
- **Épico** — uso restrito; recompensas ou componentes de importância elevada.

### Reservadas para o futuro
- **Lendário** — estrutura prevista, mas não deve gerar conteúdo nesta fase.
- **Secreto** — não desenvolver nesta fase.

### Sagrado não é degrau de raridade
`Sagrado` deve ser tratado como **propriedade/natureza** quando aplicável, e não automaticamente como raridade superior. Um item pode ter uma raridade e, separadamente, possuir natureza sagrada.

**Regra:** não criar um item apenas para preencher uma raridade. Primeiro existe uma necessidade real de gameplay; depois o item recebe sua classificação.

## 4. Ficha mínima de cada item

Quando uma pendência deste painel virar item efetivamente definido, sua ficha em `gdd/04-itens/` deve prever:

- ID estável `ITEM-XXX`
- nome
- categoria/tipo
- raridade
- propriedade/natureza, quando houver
- origem
- forma de obtenção
- destino/uso
- quantidade necessária, quando aplicável
- transformação ou resultado
- dependências
- estado de implementação
- imagem futura em `./assets/itens/ITEM-XXX.png`

A ausência de imagem **não bloqueia a definição documental**. O caminho visual é reservado quando o item ganhar ficha própria.

## 5. Linha de quitação

A ordem abaixo é a fila principal. Não avançar por impulso para novas expansões: concluir ou deliberadamente bloquear/documentar a etapa corrente antes de abrir a seguinte.

### ETAPA A — Gameplay inicial de John

**Já existentes/documentados**
- [x] Madeira Comum — ITEM-001.
- [x] Madeira Sagrada — ITEM-002; recebida diretamente de Eldrin, sem obrigação de representação física durante a entrega.
- [x] Espada de Madeira Sagrada — ITEM-003.

**Pendências desta fase**
- [ ] **Escudo inicial** — equipamento defensivo inicial. Nome, origem, materiais e atributos: A DEFINIR.
- [ ] **Proteção corporal inicial** — conceito provisório de colete/gibão leve, apelidado informalmente de “colete de vidro” por sua fragilidade; não é feito de vidro. Nome definitivo, origem, materiais e atributos: A DEFINIR.
- [ ] Definir como escudo e proteção entram na sequência inicial sem alterar o que já está validado da obtenção da espada.

**Critério de quitação:** os equipamentos iniciais aprovados existem, podem ser obtidos/equipados, foram testados e estão VALIDADOS.

### ETAPA B — Oficina de Mestre Cedric / Forja

**Já existente**
- [x] Cedric e sua oficina possuem papel canônico na criação da Espada de Madeira Sagrada.

**A definir e produzir**
- [ ] Confirmar quais objetos da oficina serão **interações funcionais**, distinguindo-os da decoração.
- [ ] Definir estação/interação de fabricação ou aprimoramento, caso necessária.
- [ ] Definir materiais comuns de forja realmente necessários.
- [ ] Definir materiais raros somente quando uma receita ou aprimoramento aprovado exigir.
- [ ] Definir componentes consumidos por cada aprimoramento.
- [ ] Definir o que Cedric entrega ao jogador em cada serviço aprovado.
- [ ] Definir representação física/visual dos materiais que possam aparecer em coleta, entrega, fabricação ou recompensa.
- [ ] Conectar receitas aprovadas ao inventário e ao equipamento correspondente.
- [ ] Testar e validar o ciclo completo de entrada → consumo → resultado.

**Nota:** exemplos como “metal sagrado”, quantidades específicas ou níveis de arma discutidos em conversa **não são canônicos** até aprovação individual.

### ETAPA C — Boticário

- [ ] Auditar o boticário existente e separar decoração de interação funcional.
- [ ] Definir o primeiro recurso vegetal necessário.
- [ ] Definir recursos adicionais somente se uma receita real exigir.
- [ ] Definir recipientes/componentes que precisem existir como itens.
- [ ] Definir primeiro produto/consumível e sua utilidade.
- [ ] Definir origem de cada recurso sem recorrer à Fazenda nesta fase.
- [ ] Criar representações físicas/visuais dos coletáveis aprovados.
- [ ] Implementar coleta/entrega/produção.
- [ ] Testar e validar a cadeia completa.

**Não canonizar automaticamente:** poções, antídotos ou efeitos específicos citados apenas como exemplos anteriores.

### ETAPA D — Pesca / Lucan / Cais

- [ ] Auditar quais interações de pesca já existem.
- [ ] Definir ferramenta necessária para pescar, se houver.
- [ ] Definir isca somente se tiver função real.
- [ ] Definir o primeiro pescado coletável.
- [ ] Definir variações adicionais apenas quando houver diferença real de uso/valor/receita.
- [ ] Definir destino do pescado: consumo, comércio, receita, entrega ou combinação aprovada.
- [ ] Criar representação física dos pescados coletáveis.
- [ ] Implementar obtenção → inventário → destino.
- [ ] Testar e validar a cadeia.

### ETAPA E — Madeira / Garrick / Serraria

- [ ] Auditar recurso de corte/coleta e interação existente.
- [ ] Confirmar relação entre Madeira Comum já canônica e futuros recursos da serraria.
- [ ] Definir tora somente se necessária como estágio próprio de gameplay.
- [ ] Definir madeira processada/tábua somente se houver receita ou destino.
- [ ] Definir ferramentas necessárias.
- [ ] Definir compradores/consumidores dentro da vila.
- [ ] Criar os objetos físicos aprovados.
- [ ] Implementar coleta → processamento → destino.
- [ ] Testar e validar a cadeia.

### ETAPA F — Mineração / Borin / Mina

- [ ] Auditar pontos de mineração existentes.
- [ ] Definir primeiro veio/recurso de interação.
- [ ] Definir minério comum e seu destino.
- [ ] Definir recurso raro somente quando houver uso aprovado.
- [ ] Definir ferramenta de mineração, se necessária.
- [ ] Definir processamento/refino apenas se fizer parte da cadeia real.
- [ ] Conectar materiais aprovados à forja, comércio ou outra utilidade.
- [ ] Criar representações físicas dos recursos.
- [ ] Implementar extração → inventário → destino.
- [ ] Testar e validar a cadeia.

### ETAPA G — Alfaiataria / proteção leve

- [ ] Confirmar se alfaiataria/local/NPC já existem ou permanecem lacuna documental.
- [ ] Definir materiais somente a partir de equipamentos/roupas realmente necessários.
- [ ] Definir couro, tecido, linha ou equivalentes apenas quando a receita aprovada exigir.
- [ ] Usar a proteção inicial de John como possível primeira necessidade, sem fixar receita antes da decisão.
- [ ] Criar representações físicas dos materiais coletáveis/componentes.
- [ ] Implementar fabricação/entrega/equipamento.
- [ ] Testar e validar.

### ETAPA H — Taverna

- [ ] Auditar presença e estado físico da Taverna.
- [ ] Definir interações funcionais: atendimento, entrega, compra/venda, produção ou outras aprovadas.
- [ ] Definir produtos apenas a partir de utilidades reais.
- [ ] Não puxar a cadeia produtiva da Fazenda para esta fase.
- [ ] Se um produto depender futuramente da Fazenda, registrar `DEPENDÊNCIA FUTURA — FAZENDA DE ARKAN`.
- [ ] Avaliar NPC/profissão especializada, como mestre cervejeiro, somente quando a cadeia correspondente for aprovada.
- [ ] Criar objetos físicos dos produtos/interações aprovados.
- [ ] Implementar, testar e validar.

### ETAPA I — Mercado / Armazém / Tobias

- [ ] Auditar o posto definitivo e as interações de Tobias.
- [ ] Definir quais itens já consolidados podem ser comprados, vendidos, avaliados ou entregues.
- [ ] Criar recipientes de carga como itens funcionais apenas se participarem de gameplay real.
- [ ] Não transformar caixas, sacos e barris decorativos em itens de inventário sem necessidade.
- [ ] Implementar entrada/saída de mercadorias aprovadas.
- [ ] Testar e validar.

### ETAPA J — Masmorras / loot

- [ ] Auditar os baús e demais interações físicas já existentes.
- [ ] Fazer o baú funcional somente quando a regra de loot estiver definida.
- [ ] Definir primeiro conjunto de recompensas com utilidade fora da masmorra.
- [ ] Definir materiais comuns/raros/épicos somente quando houver destino concreto.
- [ ] Reservar Lendário e Secreto para fase futura.
- [ ] Para cada drop, registrar quem consome e por quê.
- [ ] Criar representação física dos drops que aparecem visualmente ou entram no inventário.
- [ ] Implementar baú/interação → geração → coleta → inventário → destino.
- [ ] Testar e validar.

### ETAPA K — Equipamentos e aprimoramento

- [ ] Consolidar armas existentes e futuras aprovadas.
- [ ] Consolidar escudos.
- [ ] Consolidar proteções/armaduras leves.
- [ ] Definir níveis de aprimoramento somente depois das cadeias de materiais.
- [ ] Para cada melhoria, registrar equipamento-base + materiais + quantidades + NPC/estação + resultado.
- [ ] Garantir que materiais de upgrade tenham origem jogável e não existam sem função.
- [ ] Implementar, testar e validar cada caminho antes de expandir níveis.

## 6. Modelo de cadeia

Toda cadeia aprovada deve poder ser lida desta forma:

`INTERAÇÃO/ORIGEM → ITEM GERADO → INVENTÁRIO → DESTINO/NPC/ESTAÇÃO → CONSUMO/COMBINAÇÃO → RESULTADO`

Exemplo puramente estrutural, sem canonizar nomes ou números:

`Baú → material raro → inventário → Cedric → material + componente + arma-base → arma aprimorada`

## 7. Painel de progresso

| Ordem | Núcleo | Estado inicial |
|---:|---|---|
| A | Gameplay inicial de John | EM CONSOLIDAÇÃO |
| B | Oficina de Cedric / Forja | PENDENTE |
| C | Boticário | PENDENTE |
| D | Pesca / Lucan / Cais | PENDENTE |
| E | Madeira / Garrick / Serraria | PENDENTE |
| F | Mineração / Borin / Mina | PENDENTE |
| G | Alfaiataria / proteção leve | PENDENTE |
| H | Taverna | PENDENTE |
| I | Mercado / Armazém / Tobias | PENDENTE |
| J | Masmorras / loot | PENDENTE |
| K | Equipamentos e aprimoramento | PENDENTE |

A ordem pode ser alterada por decisão humana quando uma dependência real exigir, mas o painel deve continuar representando uma fila única e rastreável.

## 8. Critério para encerrar esta fase

A fase de consolidação só é considerada quitada quando:

- os itens e interações aprovados desta fila chegaram a **VALIDADO**;
- itens coletáveis possuem origem e destino claros;
- itens de interação possuem função real;
- não existem materiais criados apenas para “encher” catálogo ou raridade;
- as cadeias principais da Vila de Arkham funcionam de ponta a ponta;
- pendências deliberadamente adiadas estão identificadas como futuras, sem parecer concluídas;
- a Fazenda de Arkan continua separada para uma fase própria;
- a versão local pode então ser tratada como um conjunto coerente para validação antes de uma futura atualização pública.

## 9. Regra de manutenção

Ao concluir uma pendência:
1. atualizar o estado neste painel;
2. criar/atualizar a ficha ITEM correspondente quando houver item canônico;
3. reservar/atualizar sua imagem em `assets/itens/` quando houver arte;
4. atualizar o índice documental quando necessário;
5. registrar versão pública somente quando o conjunto planejado da etapa estiver testado e validado, evitando microversões por pequenas alterações.
