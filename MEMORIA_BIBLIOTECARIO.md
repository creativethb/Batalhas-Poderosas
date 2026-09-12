# MEMÓRIA PERSISTENTE DO BIBLIOTECÁRIO — BATALHAS PODEROSAS

> **DIRETÓRIO OFICIAL DE MEMÓRIA:** `F:\Bibliotecário_GDD`  
> **FUNÇÃO DO DOCUMENTO:** Registro consolidado, fidedigno e persistente do estado, lore canônica, mecânicas e sistemas do projeto **Batalhas Poderosas** entre sessões de desenvolvimento.  
> **ÚLTIMA ATUALIZAÇÃO:** 11/09/2026  

---

## 1. Manifesto de Trabalho do Bibliotecário

1. **Memória Externa Viva:** Sempre que uma nova sessão for iniciada, este documento é a fonte de verdade para recuperar o contexto do projeto.
2. **Atualização Obrigatória:** Qualquer sistema implementado, decisão aprovada, alteração de mecânica ou mudança estrutural relevante realizada pelo agente desenvolvedor deve ser imediatamente consolidada nesta memória.
3. **Critério de Canonicidade:** Registros marcados como `STATUS: CANÔNICO` representam decisões oficiais aprovadas pelo dono do projeto. Ideias e testes não são canônicos até aprovação explícita.
4. **Sem Duplicações e Sem Contradições:** Informações antigas substituídas devem ser atualizadas para manter a memória limpa, clara e pronta para alimentar o **GDD oficial no GitHub**.

---

## 2. Visão Geral do Projeto & Contexto

- **Universo:** Batalhas Poderosas (Saga de Fantasia Medieval).
- **Ambiente Narrativo Principal:** Vila de Arkham, no Reino de Arkan (Place ID: `82288539700831`).
- **Ambiente Laboratório / Sandbox:** Universo "Mundo Livre" (Place ID: `92821469286193`), conectado organicamente por um portal dimensional inter-place (`CavernaAcessoMundoLivre` / `Portal_MundoLivre`).
- **Plataformas-Alvo:** Multiplataforma nativa (PC, Mobile/Touch, Consoles Gamepad PlayStation & Xbox).

---

## 3. 🟢 Decisões Canônicas (STATUS: CANÔNICO)

```text
STATUS: CANÔNICO
DECISÃO: John é o protagonista da saga, soldado do Reino de Arkan, habitante da Vila de Arkham. No início da jornada ele é o único soldado de sua vila, ainda não é poderoso e precisa se preparar e evoluir.
DATA: 08/09/2026
```

```text
STATUS: CANÔNICO
DECISÃO: O jogo inicia na Casa de John. O início do gameplay foca na preparação inicial: coletar Madeira Comum na mesa de sua residência, buscar a bênção e a Madeira Sagrada com o Ancião Eldrin na Árvore Sagrada, e forjar a Espada de Madeira Sagrada na oficina com Mestre Cedric.
DATA: 08/09/2026
```

```text
STATUS: CANÔNICO
DECISÃO: O conflito central envolve a guerra de Arkan contra um Rei Mago extremamente poderoso, que no passado remoto serviu como mago ao antigo rei de Arkan antes de se corromper.
DATA: 08/09/2026
```

```text
STATUS: CANÔNICO
DECISÃO: A Vila de Arkham possui sua própria atmosfera e narrativa imersiva. O antigo sistema de "Sandbox/criações" foi desacoplado de Arkham e permanece restrito ao portal opcional do Mundo Livre.
DATA: 08/09/2026
```

```text
STATUS: CANÔNICO
DECISÃO: Padrão de UX por plataforma:
- PC / Console: tela limpa, sem botões virtuais invasivos (comandos via teclado/gamepad).
- Mobile / Touch: HUD contextual adaptativa (exploração limpa com Pulo/Dash/Sacar; combate revela Ataque/Defesa/Foco).
DATA: 08/09/2026
```

```text
STATUS: CANÔNICO
DECISÃO: Existe um diário pertencente a John. É elemento narrativo oficial de Batalhas Poderosas.
O jogador o encontra no mundo no início da gameplay. Contém poucos registros iniciais que situam o
jogador sobre: onde está, em que momento da história está, o que ocorre em Arkan, o que John sabe
sobre a ameaça e seus objetivos imediatos. É atualizado conforme John avança na história.
Será organizado em capítulos, crônicas e/ou contos acompanhando a progressão narrativa por mundos
e fases. O nome definitivo do livro e sua transformação futura em grande conto permanecem EM CONSTRUÇÃO.
DATA: 08/09/2026
```

```text
STATUS: CANÔNICO
DECISÃO: Batalhas Poderosas possui duas camadas narrativas distintas e relacionadas:
1. DIÁRIO DE JOHN — gameplay e narrativa pessoal, primeira pessoa, cronológico, ligado à experiência
   do jogador. Existe fisicamente no mundo, é coletado, entra no inventário e pode ser consultado.
   Responde: "O que está acontecendo comigo?"
2. LIVRO / LORE DO UNIVERSO — camada histórica e abrangente. Registra acontecimentos anteriores a
   John, grandes batalhas, lendas, reis, origens. Responde: "O que aconteceu neste mundo?"
Fluxo canônico: John vive → acontecimento entra no Diário → jogador consulta o novo registro.
O Bibliotecário não deve transformar automaticamente uma ideia em cânone.
DATA: 08/09/2026
```

```text
STATUS: CANÔNICO
DECISÃO: Prólogo literário oficial ("Antes das Batalhas") estabelecido como abertura canônica do
Grande Livro de Arkan (LORE-005). Registra a história remota do mago conselheiro, a traição do antigo
rei, o exílio e perda da família nas Minas, a ascensão do Rei Mago e o início da guerra da reparação
contra o novo rei descendente, convergindo para o despertar de John em Arkham.
DATA: 08/09/2026
```

```text
STATUS: CANÔNICO / CONCLUÍDO
DECISÃO: A Fazenda de Arkan é a expansão rural canônica oficial (768.000 studs²).
1. Masterplan intocável com 26 lotes, 5 setores, corredores e 32 zonas funcionais indexadas no FazendaManager
   (136 elementos no ReplicatedStorage.Fazenda_Arkan_Blueprint).
2. Peças físicas de demarcação são temporárias e removidas após validação da construção definitiva; o Blueprint
   e o FazendaManager permanecem como referência técnica (não são construções do mundo).
3. A construção da Fazenda nesta etapa está CONCLUÍDA: 26/26 estruturas e áreas catalogadas como construídas:
   Casa do Fazendeiro, Armazém de Produção, Celeiro Principal, Estábulo Rural, Galpão de Ferramentas,
   Beneficiamento, Depósito de Feno, Moinho, Curral Principal, Galinheiro, Cercado de Ovelhas, Cercado de Porcos,
   Campo de Milho, Campo de Trigo, Campo de Vegetais, Campo Variado, Pomar, Horta, Poço, Reservatório,
   Área de Carroças, Pátio Econômico, Pasto de Animais Futuros, Expansões Agrícola e Estrutural e Pátio de Carga.
4. Nenhuma área permanece PLANEJADA, PENDENTE ou EM CONSTRUÇÃO. Novas construções serão tratadas como expansões
   futuras ou novas necessidades de gameplay.
DATA: 11/09/2026
```

---

## 4. Sistemas Implementados & Operacionais

### 4.1. Sistema Imersivo de Diálogo & Câmera Cinematográfica (MISSÃO 27)
- **Fluxo Cinemático:**
  - Jogador interage via `ProximityPrompt` ("Conversar").
  - O servidor pausa imediatamente a rotina e movimentação do NPC (`WalkSpeed = 0`, física zerada).
  - O cliente conduz aproximação suave até o arco frontal ideal do NPC (~4.8 studs) e orienta o jogador 100% de frente (`dot = 1.0000`).
  - O jogador fica totalmente imóvel durante o diálogo (bloqueio de WASD, pulo, dash e ataque via `ContextActionService` e atributo `EmDialogo`).
  - A câmera transiciona suavemente via `TweenService` para enquadramento over-the-shoulder focado no rosto do NPC (`FOV = 52°`).
- **HUD Medieval Nobre (`HUD_DialogoImersivo`):**
  - Fundo escuro com degradê e moldura em ouro polido (`Color3.fromRGB(225, 185, 75)`).
  - Nome do personagem em destaque (`Antique`) e Cargo/Subtítulo (`GothamBold`).
  - Texto com efeito typewriter suave (acelerável com toque/clique/tecla).
  - Ícone de fechar nítido com `"X"`.
  - Suporte nativo completo a Gamepad: foco automático via `GuiService.SelectedObject`, navegação por D-Pad/analógico com realce dourado suave e contraste nítido (`TextStrokeTransparency = 0.40`), `ButtonA`/`ButtonX` para avançar/confirmar e `ButtonB` para fechar.
- **Camada de Dados Tipada (`ReplicatedStorage.SistemaDialogo.BancoDeDialogos`):**
  - Diálogos dinâmicos com árvores de escolhas, forja de espada, lenda sagrada e falas temáticas para todas as classes da vila.

### 4.2. Sistema de Combate & Combos de Espada (MISSÕES 13 & 17)
- **Combo Encadeado de 5 Golpes:** Hits sequenciais (1 a 5) com IDs oficiais, reset automático após 1.15s sem atacar.
- **Hitbox & Dano Espacial:** Detecção ativa de lâmina durante o golpe com remote `ProcessarDano` no `GerenciadorCombateServer`, faíscas de impacto e som de corte.
- **Grip Calibrado:** Empunhadura manual exata no cabo de carvalho.
- **Braço Livre e Relaxado:** Neutralizada a idle rígida do Roblox (`507768375`), permitindo balanço natural do braço ao andar e correr.

### 4.3. Sistema de Locomoção, Dash & Duplo Pulo (MISSÕES 04 & 13)
- **Dash & Corrida Unificados:** Toque rápido no botão = Dash; segurar = Corrida (`WalkSpeed = 28`); soltar = volta ao normal.
- **Duplo Pulo Físico:** Impulso ascendente configurado com efeito de partículas nos pés.
- **Lock-On / Foco Automático:** Tecla `R` / `ButtonR1` / Botão Mobile de Foco trava a mira e a retícula no inimigo mais próximo.

### 4.4. Sistema de Assentos Universais por Auto-Sentar (MISSÃO 09)
- **Servidor (`GerenciadorAssentosCentral`):** Detecta bancos, poltronas e cadeiras dinamicamente em runtime, cria instâncias `Seat` proporcionais com altura calibrada (`-0.45` studs para o avatar assentar suavemente sobre o estofado/madeira).
- **Orientação Anatômica:** Assentos de praça alinham de costas no encosto; bancos de taverna e casas alinham de frente para suas respectivas mesas.
- **Anti-Loop:** Cooldown de 2.0s após levantar impede re-sucção acidental ao caminhar próximo.
- **Saída Suave & Giro 180°:** Toque no direcional gira bancos sem encosto em 180°; segurar o direcional solta o personagem deslizando.

### 4.5. Portas Inteligentes Push-Away (MISSÕES 02 & 27)
- **`GerenciadorPortasCentral`:** Sistema automático que detecta jogadores e NPCs a até 14 studs e abre as portas sempre se afastando da entidade (nunca bate na cara).
- **Entrada da Padaria Desbloqueada:** Artefato residual invisível removido; portas duplas abrem e permitem passagem livre até o forno e balcão.

### 4.6. Montarias com Física Real & Animação (MISSÃO 12)
- **Charrete Nobre & Carroça:** Física unanchored com soldagem ao `HumanoidRootPart`, gravidade real no terreno, rodas com giro concêntrico perfeito e cavalo com articulação procedural das 4 patas e pescoço.

---

## 5. População de NPCs & Distribuição Territorial

Todos os 20+ NPCs da vila utilizam rig oficial **R15 com malha arredondada (Rig Base)**, sem nomes flutuantes na cabeça, com colisão suave e rotas exclusivas sem congestionamento na praça central:

| NPC | Profissão | Zona de Atuação & Rota Territorial |
|---|---|---|
| **O Rei Mago (Alric)** | Antagonista Trágico / Soberano | Domínio do Rei Mago / Fronteiras e Montanhas de Arkan (`NPC-000`) |
| **Mestre Cedric** | Ferreiro Real | Oficina da Vila (balcão e forja da Espada Sagrada) |
| **Ancião Eldrin** | Guardião da Floresta | Árvore Sagrada no bosque a oeste (entrega do Galho Sagrado) |
| **Mercador Tobias** | Mercador | Armazém de Provisões da Vila |
| **Rowan** | Guarda Sentinela | Acesso Leste até a Montanha e caminho da Mina (`RotaGuardaLeste`) |
| **Seraphin** | Guardião Místico | Bosque Leste e Portal do Mundo Livre (`RotaGuardiaoAmpla`) |
| **Borin** | Mineiro | Armazém até o interior da Mina (`RotaMineiroA`) |
| **Kellan** | Mineiro | Sul da Vila até a entrada da Mina (`RotaMineiroB`) |
| **Garrick** | Lenhador | Cabana e Serraria Nordeste (`RotaLenhadorA`) |
| **Torren** | Lenhador | Serraria e campos ao norte (`RotaLenhadorB`) |
| **Nalia** | Agricultora | Fazendas Norte e estábulo (`RotaAgricultorNorte`) |
| **Geraldo** | Administrador da Fazenda | Fazenda de Arkan — Casa do Fazendeiro, Pátio de Carga, Armazém, Beneficiamento e Celeiro (`RotaFazendeiro_Geraldo`) |
| **Eamon** | Agricultor | Campos e colinas ao leste (`RotaAgricultorSul`) |
| **Aldous** | Guarda Sentinela | Perímetro dos 6 portões da vila (`RotaGuarda`) |
| **Maelis** | Guarda | Sul e Oeste até o Santuário da Floresta (`RotaGuardaSul`) |
| **Beatrice** | Padeira | Interior da Padaria e balcão na praça (`RotaPadeira`) |
| **Lucan** | Pescador | Cais do Lago e cabana de pesca (`RotaPescador`) |
| **Hugo** | Cidadão / Agricultor | Colina da Casa e praça (`Rota_Hugo`) |
| **Mira** | Cidadã | Casas da colina leste até o estábulo (`RotaCivilPraca`) |
| **Selma** | Cidadã | Praça central e arredores do poço (`RotaCivilSelma`) |
| **Dario** | Cidadão | Taverna e bosque oeste (`RotaCivilDario`) |
| **Oren** | Cidadão | Hospedagem e casas medievais norte (`RotaCivilOren`) |
| **Bram** | Cidadão | Sul da vila, escadaria da Igreja e arredores (`RotaCivilBram`) |
| **Liora** | Cidadã | Hospedagem norte até o cais do lago (`RotaCivilLiora`) |
| **Joric** | Trabalhador | Taverna e hospedagem a oeste (`RotaTrabalhadorB`) |
| **Petra** | Trabalhadora | Armazém, sul da vila e oficina (`RotaTrabalhadorA`) |

> **Zona Proibida da Casa do John:** `Workspace.Vila.ZonaProibidaNPC_CasaJohn` possui `PathfindingModifier` com custo infinito (`NPCProibido`), garantindo que nenhum NPC entre na residência de John.

---

## 6. Geografia, Mapa & Pontos Notáveis

- **Praça Central da Vila (`X ≈ 32, Z ≈ 46`):** Poço de água, banca de pães, postes de ferro com iluminação noturna, assentos e conexões para todos os distritos.
- **Casa do John (`X ≈ 128, Z ≈ 68`):** Mobília detalhada com 22 MeshParts por IA (sem primitives soltas), bancada com Madeira Coletável, poltrona de descanso com lareira.
- **Oficina do Cedric (`X ≈ -18, Z ≈ -71`):** Placa nobre em carvalho e ferro, bigorna, bacia de têmpera, rebolo e balcão de forja.
- **Padaria da Vila (`X ≈ 71, Z ≈ -32`):** Forno a lenha, mesas externas e portas duplas funcionais.
- **Taverna & Hospedagem (`X ≈ -113, Z ≈ 14` / `X ≈ -100, Z ≈ 156`):** Salão com mesas e bancos orientados, quartos no andar superior.
- **Santuário da Floresta & Árvore Sagrada (`X ≈ -115, Z ≈ -152`):** Bosque ancestral onde reside o Ancião Eldrin.
- **Cais do Lago Nobre (`X ≈ 204→250, Z ≈ 64→140`):** Plataformas de madeira, peixes nadando, barco e posto de pesca do Lucan.
- **Minas da Montanha Leste (`X ≈ 382→484, Z ≈ -248→-332, Y ≈ 114`):** Galerias montanhosas, trilhos e área de extração mineral.
- **Portal do Mundo Livre (`X ≈ 339, Z ≈ -196`):** Caverna mística com sensor de aproximação que transporta para a experiência Sandbox.
- **Fazenda de Arkan (`X ≈ -10, Y ≈ 124.2, Z ≈ -1110` / `768.000 studs²`):** Polo agropecuário externo com Masterplan de 26 lotes, 5 setores e 32 zonas funcionais indexadas no `FazendaManager` (`Fazenda_Arkan_Blueprint` com 136 elementos). **26/26 construções e áreas concluídas — CANÔNICO/CONCLUÍDO** — incluindo: Casa do Fazendeiro, Armazém de Produção, Celeiro Principal, Estábulo Rural, Galpão de Ferramentas, Beneficiamento, Depósito de Feno, Moinho, Curral Principal, Galinheiro, Cercado de Ovelhas, Cercado de Porcos, 4 campos agrícolas (Milho, Trigo, Vegetais, Variado), Pomar, Horta, Poço, Reservatório, Área de Carroças, Pátio Econômico, Pasto de Animais Futuros, Expansões Agrícola e Estrutural e Pátio de Carga.
- **Acampamentos Militares Externos (`X ≈ -231, Z ≈ 708` e `X ≈ -690, Z ≈ -334`):** Postos de vigia distantes nas bordas do mapa.

---

## 7. Itens & Economia Básica

- **`Madeira Comum` (Item ID: `Madeira` / `ITEM-001`):** Coletada na mesa principal de residências marcadas com `BP_ResidenciaMadeira`.
- **`Madeira Sagrada` (Item ID: `MadeiraSagrada` / `ITEM-002`):** Ramo ancestral concedido pelo Ancião Eldrin na Árvore Sagrada.
- **`Espada de Madeira Sagrada` (Item ID: `EspadaMadeira` / `ITEM-003`):** Forjada na bigorna de Mestre Cedric consumindo 1 Madeira Comum + 1 Madeira Sagrada. Arma com Mesh IA e brilho místico verde.
- **`Diário de John` (Item ID: `DiarioDeJohn` / `ITEM-004`):** Caderno encadernado em couro rústico encontrado na mesa de repouso no início do jogo. Item permanente e indescartável que abre a interface do Diário em tempo real.
- **Banco de Dados Central:** `ReplicatedStorage.DadosItens.BancoDeItens` (ModuleScript canônico utilizado tanto pelo servidor quanto pelo cliente).

---

## 8. Pendências e Próximos Passos (Backlog)

### 8A. Atualização de Imagens do GDD (em andamento — pausado em 12/09/2026)
**Objetivo:** Substituir todas as imagens placeholder (`NPC-001.png` genérico) por retratos e ilustrações individuais.

| Status | Entidade | Arquivo | Push? |
| :--- | :--- | :--- | :--- |
| ✅ Concluído | NPC-001 — Mestre Cedric | `assets/npcs/NPC-001.jpg` | Sim |
| ✅ Concluído | NPC-002 — Ancião Eldrin | `assets/npcs/NPC-002.jpg` | Sim |
| ✅ Concluído | NPC-003 — Guarda Rowan | `assets/npcs/NPC-003.jpg` | Sim |
| ✅ Concluído | NPC-004 — Guarda Aldous | `assets/npcs/NPC-004.jpg` | Sim |
| ✅ Concluído | NPC-005 — Padeira Beatrice | `assets/npcs/NPC-005.jpg` | Sim |
| ⏳ Pendente | NPC-006 — Pescador Lucan | `assets/npcs/NPC-006.jpg` | Não |
| ⏳ Pendente | NPC-007 — Mercador Tobias | `assets/npcs/NPC-007.jpg` | Não |
| ⏳ Pendente | LOCAL-001 — Casa de John | `assets/locais/LOCAL-001.jpg` | Não |
| ⏳ Pendente | LOCAL-002 — Oficina do Cedric | `assets/locais/LOCAL-002.jpg` | Não |
| ⏳ Pendente | LOCAL-003 — Praça Central | `assets/locais/LOCAL-003.jpg` | Não |

**Formato:** JPG, 800×450px (16:9). Usuário salva na pasta `assets/npcs/` ou `assets/locais/` e avisa o nome. Agente renomeia, atualiza `index.html` e faz push.

**Pendência técnica:** Resolver cache do navegador (imagens não atualizam sem navegação anônima). Solução: adicionar meta tags de cache-busting ou query string versionada no `index.html`.

### 8B. Outras pendências do backlog

1. **Animações Personalizadas:**
   - Preencher `ID_ANIMACAO_CONVERSA_PADRAO` em `ServerScriptService.ComportamentoNPC` quando o dono fornecer a animação de gesticulação de conversa em loop.
   - Preencher `ID_ANIMACAO_IDLE_NATURAL` em `MOOV TESTE` quando a animação de postura relaxada com espada na mão estiver pronta.
2. **GDD Oficial no GitHub:** Estruturar e sincronizar os documentos canônicos a partir desta memória.
3. **Persistência do Place:** Todas as alterações feitas via MCP requerem que o dono pressione `Ctrl+S` no Roblox Studio para salvar o arquivo `.rbxl`.
4. **Nome definitivo do Livro:** 🟡 EM CONSTRUÇÃO. Possibilidades: "Livro dos Conhecimentos", "Livro Sagrado", "Bíblia de Arkan", "O Conto das Batalhas Poderosas".
5. **Entradas do Diário CAP1-004 e CAP1-005:** 🟣 PLANEJADO. Aguardam definição dos eventos de gameplay correspondentes.
6. **Capítulo 4 do Livro (Multiverso):** 🟡 EM CONSTRUÇÃO. Os mundos do Multiverso não foram documentados.
7. **Relação futura Diário → Livro:** 🟡 EM CONSTRUÇÃO. Não é cânone definitivo.
8. **Origem dos poderes do Rei Mago:** 🔴 DESCONHECIDO.
9. **Destino exato da família do Rei Mago nas Minas:** 🔴 DESCONHECIDO.
10. **Localização do reino construído pelo Rei Mago:** 🔴 DESCONHECIDO.
11. **Localização exata da coleta da Madeira Comum (Casa de John / Colina Leste):** 🟡 PROVISÓRIO — não é cânone definitivo.
12. **Como o paralelo John/Rei Mago será revelado ao jogador:** 🟡 EM CONSTRUÇÃO.

---

*Documento gerado e mantido pelo Subagente Bibliotecário de Batalhas Poderosas.*
