---
id: "GAME-017"
nome: "Academia da Guilda de Arkan — Arquitetura e Formação Inicial"
status: "PLANEJADO"
funcao: "Place da academia, construção por etapas, arena modular e primeiro ciclo obrigatório de espada e escudo"
relacionados:
  - "GAME-001"
  - "GAME-009"
  - "GAME-012"
  - "GAME-014"
  - "GAME-015"
atualizado_por: "ChatGPT — consolidação de decisões do responsável"
data_atualizacao: "2026-10-18"
---

# Academia da Guilda de Arkan — Arquitetura e Formação Inicial

> **DECISÕES DE DESIGN APROVADAS EM 18/10/2026.** Esta ficha define o plano para construção e integração futuras, **não certifica sistemas implementados, construção conferida ou publicação**. A criação e o salvamento de um Place/Baseplate com o título **Academia da Guilda** foram informados pelo responsável; PlaceId, vínculo efetivo com a experiência, geometria e estado publicado **ainda precisam ser confirmados no Studio**. Não confundir GDD com evidência de execução.

## 1. Papel no universo, instituição e objetivo

- A **Academia da Guilda** é o campus de treinamento da mesma e **única** instituição de aventureiros que possui sede na vila de **Arkham**, reino de **Arkan**. **Não é outra guilda.** Ver GAME-015 e GAME-012.
- A sede na vila cuida do registro e encaminhamento para formação; o campus serve para instrução e avaliação.
- O objetivo de lançamento inicial é fechar o **ciclo completo** entre obtenção da espada/escudo, inscrição, formação, avaliação final e concessão da **Insígnia da Guilda**, que habilita progressão de acesso.
- **Primeira especialização obrigatória: Espada e Escudo** (denominação funcional de trabalho). Não oferecer seleção inicial entre Arqueiro, Pesado ou outras classes.
- O título do Place informado pelo responsável é **Academia da Guilda**; o nome conceitual da ficha é Academia da Guilda de Arkan. O nome oficial final da instituição ainda deve ser conciliado em GAME-015.
- O desenvolvimento prioriza um único circuito jogável e extensível, **sem** construir todas as especializações agora.

## 2. Fluxo narrativo e dependências

1. **Ciclo 1 — A Primeira Lâmina:** John inicia em sua casa; cumpre a sequência Cedric → Padre Mináille / Árvore Ancestral → Eldrin / Árvore Sagrada → Cedric; recebe espada de treinamento e escudo. Não alterar GAME-001 nem reescrever essa missão.
2. **Ciclo 2 — Registro e academia:** com os itens e requisitos validados, John procura a sede existente da Guilda em Arkham, registra-se como aprendiz e recebe acesso à Academia. Ele pode adiar a visita após o cadastro, mas a formação inicial é obrigatória para a habilitação.
3. Ao entrar no campus, John **surge em ponto interno seguro do térreo**, na área de chegada/recepção, não do lado de fora dos portões.
4. O instrutor conduz fundamentos de espada e escudo, desafios e prova prática na arena; sucesso final resulta na **Insígnia da Guilda** persistente, registrada e verificada no servidor (GAME-015).
5. **Ciclo 3 — Masmorra:** os **dois guardas já existentes** na entrada da masmorra de Arkham deverão consultar a habilitação de guilda no servidor e impedir o acesso caso ela não exista; liberam apenas o personagem elegível. Essa integração ainda não está implementada nesta ficha. Não realocar os guardas nem alterar a masmorra na etapa de construção.
6. A insígnia é também condição prevista para **Jogar com Amigos** e **Mundo Público**, conforme GAME-014 e GAME-015. A habilitação não significa que os modos multiplayer estejam prontos.
7. Outras especializações podem ser desbloqueadas e aprendidas mais tarde, após progresso na masmorra; exigir conclusão do primeiro piso ou de ambos os pisos **não foi decidido**.

### Separação entre registros

- **Inscrição:** vínculo do personagem à Guilda.
- **Etapas de treino:** progresso específico da formação da jornada.
- **Insígnia:** qualificação/habilitação, não item consumível, não recompensa reaplicável em cada viagem.
- **Classe e proficiência:** habilidades e evolução distintas da insígnia.
- **Conquista global:** marco histórico da conta (ver regras mais recentes GAME-014 §10 e GAME-015 §10), não substitui progresso narrativo da jornada.
- **Patentes:** Bronze, Prata, Ouro, Diamante são apenas hipóteses de classificação futura, não catálogo ou regras aprovados.
- **PENDENTE:** definir explicitamente a relação entre insígnia/habilitação por jornada e desbloqueio de modos por conta, respeitando as três jornadas independentes. Não transferir automaticamente uma conclusão de treino para outras jornadas sem essa decisão.

## 3. Topologia e ciclo de sessão entre Places

- Campus concebido como **um Place adicional dentro da mesma experiência Roblox Batalhas Poderosas**, não uma experiência distinta, nem substituição de Place1 ou Mundo Livre.
- Place principal de referência: `82288539700831`; o PlaceId da Academia é **PENDENTE DE CONFIRMAÇÃO**.
- Primeiro foco: criar/salvar o Place em Baseplate, preparar exterior e construir academia. **Nenhum teleporte será implementado na fase arquitetônica.**
- Quando autorizado, origem do teleporte: Guilda em Arkham; destino: área segura de chegada interna na Academia. Retorno seguro: Guilda/posição validada em Arkham, com continuidade de jornada, sem duplicar inventário/moedas/estado.
- **Sessão de treino individual** mesmo para jogador vindo de ambiente multiplayer: abordagem planejada é **servidor reservado por aprendiz**, com validação no servidor de origem e no destino. Estudar uso de `TeleportService:TeleportAsync()` e `TeleportOptions.ShouldReserveServer` no momento da implementação; o mecanismo final exige inspeção técnica e testes em ambiente publicado de teste, não apenas Studio.
- Uma única construção/campus e um Place da Academia podem servir múltiplas sessões individuais; **não** criar um Place por classe nem por jogador.
- Proteção contra entrada direta indevida, ausência de dados, desconexão, duplicação de recompensa, salvamento concorrente e retorno após falha ficará para a fase de integração.
- Ponto temporário `SpawnLocation` de testes não equivale ao ponto definitivo de chegada do teleporte.

## 4. Conceito arquitetônico aprovado

### 4.1 Implantação geral

- **Edifício principal monumental térreo**, conectado por acesso/corredor ao **coliseu circular de treinamento**, aberto ao céu.
- Coliseu com piso central amplo, muralhas de contenção, portão e circulação segura; **a arena não precisa ter divisórias físicas para cada desafio**.
- Áreas construídas internas: **chegada/recepção**, **grande salão**, **sala de instrução**, corredores, espaços de apoio/reserva e acesso ao coliseu. As funções exatas das salas de apoio deverão seguir revisão final da planta, sem invenção de dependências.
- **Porta de futura escadaria/pavimento superior**: acesso arquitetônico fechado/fictício, sem escada nem segundo andar construídos. Se houver expansão vertical, redesenhar a área antes de executar.
- Entrada externa e portões podem compor a arquitetura, embora **o fluxo normal de chegada do aprendiz seja interno**.
- Exterior além da muralha tem função principalmente **cênica, não explorável** na versão inicial: gramado, pequenas ondulações, vegetação moderada, colinas de fundo, sem floresta excessiva.
- Reservar área para módulos/anexos futuros, sem construir nesta fase salas e arenas de outras classes.
- A estética e a **paleta devem ser conferidas diretamente na Guilda já existente no Place principal**, para manter continuidade institucional. Não presumir cores exatas nem inventar identidade nova.
- Direção visual: medieval estilizado adequado ao Roblox, pedra/madeira e materiais coerentes, arquitetura limpa e proporcional; evitar ultra-realismo, sci-fi/neon e detalhes de custo excessivo.

### 4.2 Referências dimensionais de estudo, NÃO homologadas

| Elemento | Estimativa preliminar | Observação |
|---|---:|---|
| Baseplate/terreno disponível | conforme Place real | Baseplate foi descrito como muito grande; medir antes de modificar |
| Reserva do complexo | cerca de 500 × 450 studs | estudo inicial, pode variar conforme implantação |
| Edifício principal | cerca de 160 × 100 studs | apenas térreo |
| Grande salão | cerca de 80 × 55 studs | conferir encaixe e circulação na planta |
| Recepção | cerca de 45 × 30 studs | ponto interno de chegada futura |
| Sala de instrução | cerca de 55 × 45 studs | conferir encaixe e circulação |
| Coliseu | cerca de 180 studs de diâmetro **interno** | formato circular, piso útil livre |
| Muralha do coliseu | cerca de 26 studs de altura | espessura, portões e raios ainda a definir |
| Corredores principais | cerca de 14 studs de largura | salvo acesso específico detalhado na planta |
| Corredor edifício-coliseu | cerca de 20 studs de largura | valor preliminar, sujeito a compatibilização |

**Não converter a tabela diretamente em peças.** Não existem ainda cotas executivas verificadas para cada parede, espessura, vão, centro/raio externo do coliseu ou altura de fundação. As primeiras imagens produzidas durante o planejamento tiveram **erros de escrita, sobreposição visual de pisos e paredes e divergências de geometria**. Portanto, **não são fontes construtivas aprovadas**. O mapa/PDF posterior enviado ao responsável é **referência de implantação preliminar**, a auditar; não presumir que já resolveu todas as coordenadas. O agente deve comparar PDF, medidas e ambiente real, relatar inconsistências e pedir validação antes de improvisar.

### 4.3 Geometria a fechar antes de execução estrutural completa

- Origem e orientação dos eixos X/Z e cota Y da fundação e do piso acabado.
- Retângulo efetivo do edifício, divisão de ambientes, espessuras e alturas das paredes.
- Larguras/posições de portas e vãos, corredores contínuos e livre circulação.
- Centro do coliseu, raios interno e externo, espessura/altura da muralha e localização dos portões.
- Encaixe do corredor com os dois edifícios, pisos sem atravessar paredes, ausência de vãos cegos.
- Distâncias às muralhas do perímetro e áreas de expansão; limites não exploráveis.
- Vista aérea **sem telhados derivada da MESMA geometria** da planta baixa, não outra ilustração inventando salas.
- Identidade de materiais e cores do edifício existente da Guilda.

## 5. Construção física: precede qualquer gameplay

**Ordem de execução aprovada**, sempre com conferência do responsável entre marcos:

| Marco | Entrega | Situação em 18/10/2026 |
|---|---|---|
| ACA-00 | Novo Place/Baseplate vinculado à mesma experiência e salvo | **RELATADO PELO RESPONSÁVEL; vínculo e PlaceId a verificar** |
| ACA-01 | Inspeção do Baseplate e preparação leve do terreno externo, reserva da área central | **SOLICITADO/PLANEJADO; conclusão não verificada** |
| ACA-02 | Compatibilização da planta em coordenadas, níveis e medidas, sem improvisos | **PENDENTE** |
| ACA-03 | Fundações, pisos e perímetro arquitetônico | **PENDENTE** |
| ACA-04 | Paredes internas/externas, portões, corredor, coliseu, portas e acessibilidade | **PENDENTE** |
| ACA-05 | Fachadas, cobertura apenas do edifício, materiais e paleta alinhados à Guilda | **PENDENTE** |
| ACA-06 | Inspeção física no Studio, correções e aceite da arquitetura | **PENDENTE** |
| ACA-07 | Estrutura modular para desafios de espada e escudo | **PENDENTE; somente após aceite arquitetônico** |
| ACA-08 | Registro, teleporte, sessão individual, treinamento, avaliações, insígnia e guardas | **PENDENTE; etapa de sistemas separada** |
| ACA-09 | Teste integral e validação do ciclo entre os Places | **PENDENTE** |

**Etapa de exterior (ACA-01):** manter ou ajustar o Baseplate somente após medi-lo; reservar piso central plano; entorno cênico com grama, ondulações e colinas discretas; não colocar scripts, NPCs, edificações nem barreiras temporárias gigantes. A muralha perimetral será posicionada após compatibilização da implantação.

**Política para agentes:** confirmar Place ativo antes de editar; preservar Place principal, Mundo Livre e sistemas existentes; não editar GDD durante a obra sem solicitação; não publicar sem autorização; não tratar pedido de construção como permissão para criar scripts, mecânicas ou itens. Relatar dimensões finais e divergências por etapa, com evidência do que realmente foi executado.

## 6. Coliseu modular e desafios — DESIGN FUTURO

- **Uma arena física fixa**, sem necessidade de construir novos pátios para cada etapa.
- Preparar, quando chegarmos aos sistemas, pontos de encaixe/catálogo de configurações por classe e etapa; modelos temporários carregam e são removidos pelo servidor.
- Exemplo de nomes **técnicos provisórios**, não estrutura de arquivos obrigatória: `EspadaEscudo_01`, `EspadaEscudo_02`, etc. Não construir antecipadamente sistemas de carregamento complexos.
- Somente a formação inicial de espada e escudo terá conteúdo jogável no primeiro ciclo.
- **Proposta preliminar de quatro desafios**, a ajustar após inspeção do combate realmente existente: (1) ataques/fundamentos, (2) defesa e bloqueio, (3) movimento/esquiva, (4) prova final em duelo supervisionado. Não pressupor funções de combate que ainda não foram verificadas.
- O instrutor fornece contexto e avalia ações; NPC, animações, critérios objetivos, número de tentativas, dano e recuperação **a especificar**.
- Futuramente, novos módulos (Arqueiro, Combatente Pesado) podem usar a arena se forem compatíveis com suas exigências. Arqueria de longo alcance pode exigir anexo específico; não prometer que todas as classes caberão no círculo atual. Criaturas da masmorra em contenção são **possibilidade distante**, não conteúdo aprovado para a versão inicial.

## 7. Transições de avaliação e interface — DESIGN FUTURO

1. Jogador executa a etapa ativa na arena.
2. Servidor valida sucesso/falha, registra estado elegível e interrompe ações da etapa.
3. **Aprovado:** oferecer **Próxima etapa** e **Encerrar treinamento**; ao concluir a última etapa, apresentar resultado da formação e concessão validada da insígnia, não uma etapa inexistente.
4. **Reprovado:** oferecer **Tentar novamente** e **Encerrar treinamento**.
5. Se continuar/repetir: fade para preto no cliente, desmontagem dos objetos temporários, montagem da configuração pertinente e reposicionamento seguro; clarear somente após o servidor confirmar prontidão.
6. Se encerrar: sair por fluxo narrativo seguro, preservando progresso confirmado e sem conceder insígnia antecipadamente.
7. **Proposta a validar:** preservar etapas concluídas para retomada posterior sem refazer todo o curso; persistência por jornada, checkpoint e política de abandono devem ser decididos antes de programar.
8. Não permitir reaproveitar recompensa com solicitações repetidas do cliente, troca de sessão ou reconexão; decisões de resultado são do servidor.
9. Textos e layout finais, acessibilidade, mobile/controle e animações de fade ainda não definidos.

## 8. Dependências técnicas e proteções para integração

- Preservar os dados de cada jornada e conquistas globais conforme GAME-014 §10 e GAME-015 §10.
- Validar existência/conclusão de *A Primeira Lâmina*, cadastro, treino e acesso ao Place em autoridade de servidor; não confiar em botão ou marcação visual.
- Usar a mesma origem persistente de inventário/economia já definida pelo jogo, nunca criar perfil duplicado da Academia.
- Tratar idempotência da insígnia, transição interrompida, falha de reserva, queda de conexão, salvamento concorrente, repetição de prova e retorno sem perda de itens.
- Os guardas devem consultar o estado autorizado, sem trocar suas identidades, posições ou responsabilidades atuais sem inspeção.
- Teste de teleporte entre Places e servidor reservado deve ocorrer em experiência publicada de **teste**, com permissão explícita, evitando publicar conteúdo de produção sem autorização.
- Produzir critérios observáveis: chegada na recepção, percurso até coliseu, desafios individuais, resultado correto, reentrada após saída e guardas respeitando a habilitação.

## 9. Limites, pendências e decisões ainda não fechadas

1. PlaceId, vínculo do novo Place à experiência e dimensões reais do Baseplate.
2. Planta executiva rigorosa: coordenadas, cotas Y, espessuras, portas e posição dos portões.
3. Paleta exata e elementos arquitetônicos da sede existente.
4. Identidade/diálogos do responsável pelo cadastro e do instrutor; sem inventar NPC canônico.
5. Critérios objetivos das quatro etapas e prova final, usando combate efetivamente existente.
6. Progresso de treino em cada jornada, elegibilidade global para modos e reconciliação com insígnia.
7. Retomada após desistência, repetição de etapa e falha na transferência.
8. Nomes definitivos de classe, insígnia, patente e conquista; a conquista **Aventureiro de Arkham** permanece nome de trabalho do GAME-015.
9. Exigência de masmorra para outras classes; progressão de patentes e habilidades especiais.
10. Limites de capacidade/desempenho dos módulos e adaptação para novas especializações.

**Regras de mudança:** alterações posteriores à arquitetura física precisam atualizar a planta técnica e a vista aérea de forma sincronizada; alteração em requisitos de formação, insignia ou abertura da masmorra exige conciliação com GAME-001, GAME-014 e GAME-015. Nenhum marcador **VALIDADO** sem evidência e aceite expresso do responsável.

## 10. Critério de conclusão do primeiro ciclo

A primeira entrega jogável será considerada completa **somente** quando houver evidência de: missão inicial e espada/escudo → cadastro na Guilda → teleporte de ida seguro → entrada interna da Academia → instrução/desafios e avaliação → insígnia persistida uma única vez → retorno seguro → guardas da masmorra liberando apenas quem tem habilitação; mais verificação das restrições de acesso multiplayer previstas.

**Situação atual:** objetivo e arquitetura planejados; implementação de formação, teleporte, insígnia, controle dos guardas e novas classes **não verificada/não concluída**.


## 11. Registro de execução informado pelo agente estrutural — 18/10/2026

> **FONTE:** relatório textual do agente *Antigravity AI — Engenheiro Chefe de Arquitetura Luau*, fornecido pelo responsável em 18/10/2026, intitulado **“RELATÓRIO DE AUDITORIA TÉCNICA E CONFORMIDADE ESTRUTURAL”**. O agente emitiu laudo “APROVADO COM LOUVOR” e declarou 100% de navegabilidade. **Essas são alegações do relatório, não homologação independente do responsável ou inspeção direta deste registro.** Capturas referenciadas em caminhos locais do computador do agente não foram abertas/verificadas nesta atualização.

### 11.1 Identificação e escopo relatados

- **Place ID de trabalho informado:** `118729171012472` (`Lugar de yagoblox1008: 10182026_2`); conferir diretamente associação à experiência antes de eventual publicação ou teleporte.
- **Modelo raiz informado:** `Workspace.AcademiaDaGuilda`; **459 Parts/Models** relatados, separados nos quatro setores abaixo.
- Terreno preservado: Baseplate **2.048 × 2.048 studs**, superfície **Y = 0**, reserva central **X = −250 a +250**, **Z = −225 a +225**; paisagismo exterior informado como intacto.
- Envelope construído informado: **X = −96 a +96**, **Z = −200 a +151**.
- Grama procedural sob os pisos teria sido eliminada com tratamento localizado de Terrain.
- **Sem gameplay, NPCs, interfaces, teleporte ou mobiliário definitivo** segundo o agente; não confundir com teste independente de ausência de scripts.

### 11.2 Dimensões executadas segundo o laudo

| Setor | Dimensões e posição relatadas | Observação |
|---|---|---|
| Edifício principal | **160 × 100 studs**; X −80 a +80, Z −200 a −100 | Telhado básico em duas águas, altura máxima relatada 44,8 |
| Recepção e Spawn | **50 × 30**; X −25 a +25, Z −200 a −170; Spawn `(0, 1.5, −185)` | Ponto de testes interno; não equivale a teleporte configurado |
| Vestíbulos oeste/leste | Cada um **55 × 30** | Frente do edifício |
| Grande Salão | **80 × 55**; X −40 a +40, Z −170 a −115 | Eixo central |
| Sala de Instrução | **40 × 55**; X −80 a −40, Z −170 a −115 | Ala oeste |
| Sala Reservada | **40 × 55**; X +40 a +80, Z −170 a −115 | Ala leste |
| Sala de Apoio | **40 × 15**; X −80 a −40, Z −115 a −100 | Ala norte-oeste |
| Escada Futura | **40 × 15**; X +40 a +80, Z −115 a −100 | Fechada, **sem escada nem segundo pavimento** |
| Galeria Norte | **80 × 15**; X −40 a +40, Z −115 a −100 | Acesso ao corredor |
| Corredor edifício-arena | **20 de largura interna × 65 de comprimento**, X −10 a +10, Z −100 a −35 | Altura relatada de 16 |
| Coliseu | **180 de diâmetro interno**, centro X 0 / Z +55 | Piso aberto ao céu; raio interno 90 |
| Muralha da arena | **6 de espessura**, raio externo 96, **192 de diâmetro externo**, 26 de altura, ameias a Y 29 | 64 segmentos construtivos relatados |
| Pórtico de acesso | **20 de vão livre × 18 de altura**, Z −35 | Inspecionar encontro com a muralha e condição da grade |

**Observação de geometria:** o extremo sul teórico do círculo externo está em **Z = −41**, enquanto o corredor termina em **Z = −35**. Isso pode representar uma conexão atravessando a espessura da muralha, mas requer inspeção do encontro do portal, das colisões e dos acabamentos. Não declarar falha ou conformidade sem observar o modelo.

### 11.3 Organização informada no Workspace

```text
Workspace.AcademiaDaGuilda
├── 01_Fundacoes_E_Pisos             [15 instâncias relatadas]
├── 02_Edificio_Principal            [134 instâncias relatadas]
├── 03_Corredor_Acesso_Arena         [56 instâncias relatadas]
└── 04_Coliseu_Arena                 [254 instâncias relatadas]
```

Soma informada dos setores: **459**. Nomes e organização são referências para o agente de refinamento; antes de editar, conferir a hierarquia real no Studio.

### 11.4 Evidências/testes declarados, sem homologação independente

O relatório declarou uma bateria de **11 checkpoints** de circulação por raycasts: chegada/spawn, recepção, salão, salas laterais, apoio, galeria, corredor, pórtico, arena e bloqueio da futura escada. Todos constam como aprovados pelo próprio agente. Também alegou ausência de z-fighting, vedação de cobertura, alinhamento de pisos, uso de gravação no histórico e oito capturas de telas do Studio, referenciadas por caminhos locais `C:/Users/User/.gemini/antigravity/brain/.../media_0.jpg`. **Essas capturas não foram anexadas nem inspecionadas nesta atualização.** Teste automatizado de varredura não substitui teste de personagem real, revisão visual nem aceite humano.

### 11.5 Controle dos marcos a partir do relatório

| Marco | Estado documental em 18/10/2026 |
|---|---|
| ACA-00 | Place ID informado; vínculo/publicação ainda exigem conferência |
| ACA-01 | Terreno relatado preparado; preservar e conferir |
| ACA-02 | Planta operacional aplicada segundo agente; conformidade precisa de inspeção |
| ACA-03 | **Construção relatada concluída**, aguardando inspeção |
| ACA-04 | **Construção relatada concluída**, aguardando inspeção |
| ACA-05 | **Coberturas e estrutura básica relatadas concluídas**, aguardando inspeção |
| ACA-06 | **AGUARDANDO VALIDAÇÃO VISUAL E ACEITE DO RESPONSÁVEL** |
| ACA-07–ACA-09 | **PENDENTES**; não avançar para gameplay apenas com este laudo |

**Próxima ação acordada:** realizar auditoria visual no Roblox Studio (pelo menos vista aérea sem telhado, fachada, recepção/spawn, salões, corredor/portão e arena), conferir escala, piso, fechamento de coberturas, portas e navegação real. Só depois autorizar refinamento arquitetônico. Nesta fase posterior, separar **acabamento/fachadas/iluminação** de **mobiliário** e de **gameplay**. Não publicar e não substituir os dados de planejamento por suposições.

**Histórico:** preservar o laudo do agente como fonte de evidência relatada; homologação final permanece reservada ao responsável.
