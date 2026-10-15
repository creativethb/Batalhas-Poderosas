---
id: "GAME-001"
nome: "Loop Principal e Progressão de Gameplay"
status: "CANONICO"
relacionados:
  - "ITEM-007"
  - "LORE-002"
  - "NPC-001"
  - "NPC-002"
  - "NPC-014"
  - "NPC-030"
  - "ITEM-001"
  - "ITEM-002"
  - "ITEM-003"
  - "DOS-004"
  - "BP-2026-009"
  - "GAME-014"
  - "GAME-015"
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Loop Principal e Progressão de Gameplay

## 1. Loop Central
O ciclo de jogo equilibra:
1. Exploração & Coleta.
2. Artesanato & Preparação.
3. Combate & Missões.

## 2. Fase 1: preparação de John

### Fluxo narrativo/gameplay aprovado para desenvolvimento — 12/10/2026
1. Na primeira missão **A Primeira Lâmina**, John procura Mestre Cedric para obter uma espada de treinamento.
2. Cedric explica que precisa de **uma Madeira Ungida** e **um galho da Árvore Sagrada (Madeira Sagrada)**. Ele orienta John a procurar o padre na igreja, mas **não revela onde obter a Madeira Sagrada**.
3. Padre Mináille revela que, atrás da igreja, existe a **Árvore Ancestral**, árvore muito antiga de origem desconhecida, possivelmente vinda de um reino distante segundo a tradição oral. Sua forma e suas folhas são inteiramente quadradas, diferentes de todas as árvores conhecidas, inclusive da Árvore Sagrada.
4. Aos pés da Árvore Ancestral há um pedaço de madeira bruta, quadrada, que John recolhe. Para diferenciar origem e transformação, o item bruto pode ser apresentado como **Madeira da Árvore Ancestral**; sua nomenclatura definitiva no inventário ainda será validada.
5. John retorna ao padre, que unge o material. O item resultante é **Madeira Ungida**.
6. John pergunta ao padre onde obter o galho da Árvore Sagrada. O padre o encaminha ao **Ancião Eldrin**, no santuário da Árvore Sagrada.
7. John obtém a **Madeira Sagrada** com Eldrin e retorna a Cedric.
8. Cedric confere e consome **1 Madeira Ungida + 1 Madeira Sagrada**, fabrica a primeira espada de treinamento e entrega **um Escudo de Madeira (ITEM-007)** como cortesia única.
9. A missão é concluída individualmente e de forma persistente. O diálogo introdutório de Cedric deixa de ser oferecido a esse jogador, inclusive em sessões futuras. Cedric passa a oferecer seus serviços habituais, como manutenção e melhorias, à medida que forem implementados.

### Estado de implementação — conferência em 15/10/2026

**IMPLEMENTADO e TESTADO localmente**, com refinamento do trecho do padre em 13/10. O ciclo Cedric → Padre Mináille → coleta atrás da igreja → unção → encaminhamento a Eldrin → Madeira Sagrada → Cedric está funcional. A antiga indicação de adiamento foi superada pela execução autorizada.

- `MissaoInicialService` e os sistemas existentes de diálogo, inventário, bússola e persistência controlam o progresso individual. A conversa de Cedric e a primeira forja foram preservadas.
- Coleta em `Workspace.Vila.05_IgrejaDeArkham_V1.MadeiraColetavelIgreja`; árvore real referenciada por `ArvoreAncestralReferencia.Value`. O destaque e a retirada visual são individuais.
- O cadastro-base é `madeira_comum`; a unção muda estado/apresentação para **Madeira Ungida**, sem duplicar a quantidade. `madeira_sagrada` continua separado.
- Cerimônia provisória de 2,4 s, validação de material/estado/proximidade no servidor e token por jogador. Interrupção antes do commit não transforma a madeira.
- Após a unção, o objetivo permanece no padre até concluir a conversa. `ProgressoFase1.PadreEncaminhouEldrin` conserva o encaminhamento entre sessões.
- Cedric consome 1 Madeira Ungida + 1 Madeira Sagrada e concede uma espada e um Escudo de Madeira (ITEM-007), sem repetir a recompensa.
- Notificações de missão usam a apresentação existente e esperam a confirmação do jogador; a bússola acompanha o objetivo real.

**Testes registrados:** 24 verificações de serviços com armazenamento isolado em memória; Play passando pelos callbacks e remotos reais desde o menu até a forja; interrupção/retomada da unção; repetição recusada; independência de dois perfis simulados. Os deslocamentos entre os locais foram posicionados para teste, não percorridos integralmente a pé. Reconexão física, dois clientes reais e dispositivos físicos continuam pendentes. Não marcar como VALIDADO.

O refinamento da missão foi publicado no Place em 13/10/2026 às 15:31:09, após autorização específica. Isso não comprova publicação de refinamentos posteriores da interface. A presente atualização é documental.

**Pendências:** modelos definitivos, revisão artística, balanceamento e homologação real de rede. A antiga coleta na casa/comércio não é a rota ativa. O registro histórico BP-2026-002 foi substituído por BP-2026-009.

## 3. Princípio do arco
As etapas adicionais não existem apenas para alongar o tutorial. Cada deslocamento deve apresentar uma parte da vila, fortalecer relações com seus moradores e dar significado à fabricação da primeira espada deste ciclo.

Madeira Ungida e Madeira Sagrada são materiais distintos:
- Madeira Ungida: madeira comum obtida por John e depois ungida pelo padre.
- Madeira Sagrada: galho proveniente da Árvore Sagrada e ligado a Eldrin.

## 4. Inicialização e liberação do jogador

Fluxo atual: **Menu Principal → Solo → abertura cinematográfica recorrente → cutscene de John, apenas se pendente → fade → gameplay**. O menu não exige assistir à abertura antes de escolher o modo.

O perfil único usa `Narrativa.IntroducaoJohnConcluida`, sem inferir conclusão pela primeira espada ou existência de save. A confirmação ocorre no ponto seguro da cutscene, sob o fade, após posicionamento na área livre à frente da escrivaninha. Interromper antes disso mantém a cena pendente. Retornos usam `CasaJohnFrenteEscrivaninha`, sem afirmar restauração da última coordenada.

Só há liberação após prontidão do cliente, perfil, Fase1 e confirmação do servidor. Se a abertura acabar antes, a cobertura de carregamento permanece. A posse dos itens persiste, mas cada entrada começa sem equipamentos vestidos/sacados, conforme decisão aprovada. Ver GAME-014 para componentes, medições locais e limites.

## 5. Áudio

O menu reutiliza o tema da vila (`106121868942949`) em loop, com volume moderado e controle de contexto. Abertura, cutscene e vila não devem sobrepor as músicas. O áudio atual da cutscene (`86574858496121`) deve tocar até o fim antes da entrada da música ambiente. Narração do primeiro registro do diário é distinta (`90096381155243`, GAME-005). A antiga anotação de download inválido da música da vila não descreve a configuração atual.

## 6. Universo único, formação na guilda e modos de sessão — aprovado em 13/10/2026

**Decisão de design aprovada; Solo e menu implementados, modos multiplayer pendentes:** o jogo preservará uma campanha e um perfil persistente por jogador em três tipos de entrada: Solo desde o começo; grupo privado com convites controlados pelo líder; mundo público para exploração e atividades compartilhadas. Progressão, inventário, economia, missões, classes e conquistas acompanham o jogador entre sessões. Cenas exclusivas de John (incluindo a casa e o diário) devem ocorrer em contexto pessoal sem interferir na vila compartilhada. **Ver GAME-014**, que contém regras de entrada, menu, carregamento, bloqueios e pendências técnicas.

O primeiro ciclo de formação inclui **A Primeira Lâmina** já definida acima e, futuramente, cadastro/treinamento na guilda, primeira classe e concessão persistente da **Insígnia da Guilda**. Só então são desbloqueados **Jogar com Amigos** e **Mundo Público**, também validados no servidor. As classes são **múltiplas por personagem**, com pontos de habilidade distribuídos individualmente e novas especializações registradas na **Carteira da Guilda**, sem escolha permanente obrigatória. **Ver GAME-015** para a distinção entre guilda, grupo, classes, conquista e desbloqueio.

**Estado de trabalho:** o trecho do padre/Árvore Ancestral foi implementado e refinado. Formação na guilda, classes, insígnia e modos multiplayer continuam futuros. Não confundir a conclusão da primeira espada com a implementação de toda a formação. O Place ainda é único; não houve migração ou teleporte nesta etapa.
