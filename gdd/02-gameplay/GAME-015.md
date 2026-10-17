---
id: "GAME-015"
nome: "Guilda de Arkham, Carteira, Classes e Conquistas"
status: "PLANEJADO"
funcao: "Formação do aventureiro, primeira insígnia, desbloqueio multiplayer e progressão multiclasse"
relacionados:
  - "GAME-001"
  - "GAME-009"
  - "GAME-012"
  - "GAME-014"
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Guilda, Carteira do Aventureiro, Classes e Conquistas

> **CONCEITO APROVADO EM 13/10/2026; IMPLEMENTAÇÃO DA FORMAÇÃO/CLASSES/DESBLOQUEIO PENDENTE.** Não confundir com serviços de venda de espólios/tesouraria já descritos no GAME-012.

## 1. A instituição
Há **uma única guilda de aventureiros na vila de Arkham**. É uma instituição do mundo para cadastro, treinamento, missões e reconhecimento de aventureiros. Sua denominação oficial ainda precisa ser conciliada com a expressão **Guilda de Arkan** já usada no GAME-012: até validação, tratar **Guilda em Arkham / Guilda de Arkan** como referência à mesma instituição, sem criar outra sede ou segunda guilda por acidente.

Uma **equipe/grupo privado** de jogadores não equivale a uma nova guilda. O líder de sessão convida amigos, mas não controla o registro ou a progressão dos convidados na instituição.

## 2. Formação inicial e direito ao multiplayer
Uma pessoa que entra pela primeira vez só pode selecionar **Solo / Continuar História**. A sequência formativa aprovada é:
1. Abertura e narrativa pessoal na casa de John, diário e começo da aventura.
2. Primeira missão **A Primeira Lâmina**: sequência Cedric → padre/Árvore Ancestral → Eldrin/Árvore Sagrada → Cedric, com espada e escudo segundo GAME-001. **Trecho implementado e testado localmente; ver GAME-001. Formação na guilda ainda futura.**
3. Inscrição/treinamento inicial na guilda, incluindo prova de aprendizado ainda a desenhar.
4. Escolha/desbloqueio de **pelo menos uma primeira classe**, sem ficar restrito para sempre a ela.
5. Concessão permanente da **Insígnia da Guilda**, registrando conclusão da formação e conquista **Aventureiro de Arkham** (nome de trabalho para a conquista, confirmar apresentação final).
6. A insígnia ativa a elegibilidade de **Jogar com Amigos** e **Mundo Público** em todo acesso posterior, independentemente da sessão.

**A Insígnia não é um item consumível, negociável ou perdível** que possa retirar o desbloqueio. Sua posse deve ser um registro persistente no perfil/Carteira da Guilda, conferido pelo servidor. O ícone físico/visual é uma representação desse registro, não sua única fonte de verdade.

A conclusão do primeiro ciclo habilita multiplayer, **não encerra toda a campanha**. John pode adiar missões posteriores e alternar exploração, guilda, treino, comércio, fazenda, masmorras e objetivos secundários.

## 3. Carteira da Guilda
A **Carteira da Guilda** é o registro/interface pessoal central de filiação e evolução, a integrar ao menu/inventário existente sem duplicar moedas ou fontes de dados:
- identificação do aventureiro e filiação à guilda;
- Insígnia da Guilda e status de habilitação;
- classes aprendidas/desbloqueadas e especialização ativa, se pertinente;
- pontos de habilidade disponíveis, gastos e alocação por classe/habilidade;
- treinamento/qualificações e marcos/conquistas;
- evolução individual, independentemente de solo, privado ou público.

Não introduzir um sistema de ranking obrigatório da guilda como substituto de classes e carteira. A evolução permite **abrir novas classes dentro da própria carteira** conforme treinamento/requisitos.

## 4. Multiclasse e pontos de habilidade
**Decisão canônica de design:** classe não é exclusiva nem escolha permanente. O mesmo John pode estudar mais de uma especialização ao longo do tempo; cada jogador constrói uma distribuição pessoal de habilidades. Guerreiro, Arqueiro e Tanque são **exemplos**, não lista canônica fechada.

- Desbloquear classe e investir pontos são ações distintas.
- O registro das classes desbloqueadas e seus investimentos é persistente e individual.
- Ao abrir nova classe, ela passa a integrar a carteira, com habilidades elegíveis para receber pontos segundo regras futuras.
- Jogadores no mesmo nível podem ter builds diferentes, mesmo compartilhando missões.
- O jogo não exige recriar personagem, apagar nível ou refazer introdução para aprender outra classe.
- Dependências entre habilidades, acúmulo de efeitos de classes, limite de pontos, custos, redistribuição/reembolso, classe ativa e troca em combate **não estão definidos**. Não inventar esses números nem prometer combinações ilimitadas.

## 5. Conquistas, habilitações e progresso
Separar os conceitos:
- **Conquista:** marco histórico persistente do personagem (ex.: fabricar primeira espada; formar-se na guilda; primeira masmorra).
- **Requisito de desbloqueio:** condição de gameplay que habilita funcionalidade e é validada pelo servidor (ex.: insígnia para modos multiplayer).
- **Recompensa:** item, ponto ou benefício concedido uma vez conforme regra explícita.

Conquista não deve ser confundida automaticamente com uma Roblox Badge externa: integração a badges da plataforma é opcional, a decidir. A conquista interna pode aparecer em UI e carteira sem exigir integração externa. Não disparar recompensas novamente ao reentrar.

### Marco fundador
**Aventureiro de Arkham** (título provisório): concedido ao completar treino, primeira especialização e receber a Insígnia da Guilda. Notificação narrativa: **CONQUISTA DESBLOQUEADA / Aventureiro de Arkham / Jogar com Amigos e Mundo Público disponíveis**. O desbloqueio se aplica a todas as sessões.

## 6. Progressão individual em grupo
O líder controla os convites para sua sessão privada; o convidado preserva nível, classe(s), build, inventário, missões e conquistas. Se o anfitrião está adiantado, os demais não avançam automaticamente. Amigos podem acompanhar, ajudar em combate e aceitar objetivos compatíveis; um jogador pode esperar o outro ou continuar seu próprio arco. O servidor valida progressão por usuário, conforme GAME-014.

## 7. Relação com conteúdo existente
- **GAME-001:** formação de John e A Primeira Lâmina. Não alterar sequência Cedric → padre → Eldrin.
- **GAME-012:** economia e atendimento de espólios na guilda já descritos. O futuro cadastro/treinamento deve coexistir com esses postos, sem retirar suas funções.
- **GAME-009:** painel de consolidação. Registrar sistemas planejados em ordem, sem marcá-los concluídos.
- **GAME-014:** regras de sessão e desbloqueio nas três entradas.

## 8. Questões abertas para futura especificação
1. Nome público definitivo da guilda e do documento carteira.
2. Onde e com qual NPC ocorre cadastro e treinamento, quais ações constituem a prova e quando se pode treinar outras classes.
3. Conjunto inicial de classes, habilidades e requisitos; progresso por experiência e distribuição dos pontos.
4. Respec: liberdade, custos e limitações.
5. Equipamentos permitidos e combinações de habilidades; equilíbrio solo/cooperativo.
6. Visuais da carteira, insígnia, notificações e lista de conquistas.
7. Política para partidas e convites quando requisitos mudarem ou dados não carregarem.

## 9. Sequência operacional
**Planejar → construir treino básico → cadastrar primeira classe → conceder/validar insígnia → destravar botões e acesso servidor → testar persistência e reentrada → ampliar classes.** Não tentar criar todas as classes ou todas as conquistas no mesmo ciclo. Não publicar sem validação e autorização.

**Estado:** formação, classes e Insígnia continuam planejadas. A Primeira Lâmina e o menu Solo já têm implementação descrita em GAME-001/GAME-014; isso não concede os desbloqueios desta ficha. A Carteira da Guilda planejada é distinta da janela monetária CarteiraBP já existente.

## 10. Escopo das conquistas globais e progresso por jornada — 16/10/2026

**Decisão de design aprovada; implementação pendente.** As conquistas são marcos permanentes **da conta Roblox**, não dos três slots de campanha. Cada jornada conserva isoladamente seus objetivos, missões, inventário, economia e evolução narrativa. Uma conquista já obtida permanece visível no Menu Principal sem jornada selecionada, mas nunca satisfaz automaticamente um objetivo de outra jornada.

A mesma conquista não é contada duas vezes quando o acontecimento se repete em outro slot. A Partida Livre só pode conceder conquistas globais para marcos cuja elegibilidade nessa modalidade seja explicitamente aprovada; por padrão, não conceder. Títulos por quantidade de conquistas são apenas ideia futura, sem nome ou limite oficial. A **Insígnia da Guilda** permanece uma habilitação específica futura e não é substituída por títulos ou pela coleção de conquistas. Não criar conquistas ou recompensas para preencher catálogo.

A Carteira da Guilda poderá consultar registros globais quando sua implementação for autorizada, sem duplicar a fonte de verdade das conquistas. As regras de progressão das classes e da campanha permanecem próprias de cada jornada até especificação adicional. Esta seção prevalece sobre referências anteriores ambíguas a conquistas como dados exclusivos da jornada.
