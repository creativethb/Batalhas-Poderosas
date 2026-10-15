---
id: "GAME-002"
nome: "Sistema de Combate e Combos"
status: "CANONICO"
relacionados:
  - "ITEM-007"
  - "ITEM-003"
  - "GAME-001"
  - "BP-2026-005"
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Sistema de Combate e Combos de Espada

## 1. Combo atual de espada e escudo

O combo ativo usa três golpes, na ordem: `127956831239286`, `113864759585871`, `108742290977792`. O terceiro ID foi conferido no painel; a versão digitada com dígito adicional não é a animação aplicada. A antiga especificação de cinco hits não descreve o runtime atual.

## 2. Encadeamento e combo rápido

- Toques espaçados avançam 1 → 2 → 3; depois de 1,15 s sem continuação após o golpe, reinicia no primeiro.
- Dois toques dentro de até 420 ms podem acionar o clip combinado `112977567156604`, com três janelas de impacto e três sons. Um toque isolado espera 100 ms. Proteções contra entradas duplicadas/reinício do ataque são mantidas.
- Velocidades atuais dos golpes: 1,65 / 1,75 / 2; combo rápido 1,85. São ajustes provisórios de configuração, não regras canônicas imutáveis.
- Impactos no tempo original do clip combinado: 0,64–0,84; 1,20–1,42; 2,40–2,60 s. Cada janela reutiliza o contato e a proteção de um dano por alvo por golpe.
- Teste solo registrou três sons e três danos de 22 com toques separados por 383 ms. Golpes individuais, reset e rajada sem interrupção indevida também foram testados; alvo móvel, multiplayer e avaliação física mobile pendentes.

### Ataques contextuais

| Ação | Condição | Animação | Dano provisório |
|---|---|---|---:|
| Giratório leve | Foco e direção lateral ao atacar | 94997907267432 | 22 |
| Giratório concentrado | Segurar para carregar, soltar após carga válida | 135089285289341 | 34 |
| Coronhada | Defesa mantida + ataque | 102249370213198 | 14 |

Carga e impactos são validados no servidor pelo circuito existente; coronhada suspende a guarda durante o golpe e pode retomá-la se o comando continuar mantido. Testes controlados em Play confirmaram 22/34/14; controle e toque físicos/multiplayer permanecem pendentes.

### Descanso armado

Gestos longos só após 25 s parado, com espada sacada e escudo. Primeiro `133214808139172`; depois as outras variações cadastradas, com pausa de 30–45 s após cada gesto. Movimento/ação reiniciam a espera. Não são o idle base imediato. Teste local confirmou espera, pausa e interrupção por movimento; aparência específica de espreguiçar não foi certificada.

## 3. Hitbox & Validação de Dano
- **Detecção Espacial:** Varredura em tempo real (`GetPartBoundsInBox`) em torno da lâmina durante as janelas próprias de cada clip; o tempo de reprodução é considerado. A referência antiga de uma janela única de 0,28 s não se aplica a todos os golpes.
- **Validação no Servidor:** Remote `ProcessarDano` no `GerenciadorCombateServer` com proteção anti-autodano e efeitos visuais de faíscas no ponto de impacto.

## 4. Postura Natural e Braço Livre
- A ferramenta neutraliza a postura rígida nativa do Roblox (`507768375`).
- O braço de John permanece solto e relaxado para baixo, balançando de forma natural durante a caminhada e corrida.


## 5. Defesa básica com Escudo de Madeira — implementada

**ITEM-007** entra no circuito inicial como cortesia de Cedric junto à primeira espada. Exige escudo válido equipado na mão secundária; segurar o comando ergue o braço esquerdo e mantém o escudo à frente do tronco. Soltar encerra suavemente a postura.

- **PC:** botão direito do mouse ou C. **Mobile:** botão Defesa existente, por toque mantido. **Controle:** ButtonL2 mapeado, sem teste em controle físico nesta etapa.
- **Guarda frontal:** arco de 120° (±60°), validado pelo servidor; ataques comuns bloqueáveis são interceptados integralmente. Costas e lados fora do arco recebem dano normal.
- **Caminhada:** 10 studs/s na guarda, frente aos 16 habituais. Levantar o escudo encerra a corrida.
- **Ações incompatíveis:** espada, dash, corrida, segundo pulo e animações manuais de sacar/guardar não se sobrepõem à guarda. Ação já em execução impede iniciar defesa; telas exclusivas/diálogo encerram a guarda.
- **Encerramento seguro:** soltar, perder foco, desequipar, morrer, renascer ou entrar em estado incompatível limpa a defesa. O comando é renovado periodicamente e expira no servidor, evitando guarda presa.
- **Animação atual:** guarda `86391730686552`, reação `95411032570581` e parry `104279329882289`. Em movimento, preserva locomoção padrão com pose do braço esquerdo; a caminhada armada customizada é suspensa para evitar conflito. Configuração em DefesaEscudoConfig/JohnAnimacoesConfig.
- **Impacto:** pequeno recuo e som físico discreto, sem magia ou indicadores novos.

O GerenciadorCombateServer mantém o remote de dano existente e coordena solicitações de guarda/ação. A regra comum reside em SistemasGameplay.CombateDefesaService: estado autoritativo, equipamento e AplicarDano. Cada ataque comum informa sua origem no servidor; IA, alcance, cadência e progressão são preservados. Bloqueavel=false permite ignorar a guarda; QuebraGuarda=true permanece ponto de extensão, sem ataque novo criado. Armadilhas e efeitos de área mantêm o comportamento anterior.

A configuração de três golpes e o refinamento de 10/10 substituem a especificação antiga de cinco hits; valores atuais estão nas seções 1–2.

**Playtest realizado:** C/mouse direito; toque mantido no botão móvel no simulador de iPhone 17 Pro em paisagem; segurar/soltar; caminhada; frente/costas/lateral; ataque marcado como não bloqueável; Lacaio, golpe do Guardião e ácido do Vesplume reais; desequipar/requipar; conflitos com espada/dash/corrida; morte/renascimento; bolsa e interrupção de diálogo; rejeição de pose falsificada no cliente. O Play final não apresentou erros de runtime. Não houve teste de telefone/controle físicos, multiplayer ou progressão completa do Piso 2.

### Parry/reflexão — implementação e limite de testes

CombateDefesaService abre janela de 0,28 s, com intervalo mínimo de 0,85 s e uma reflexão por janela. Renovar a guarda não reabre a janela. Somente projéteis explicitamente refletíveis: secreção do Vesplume (12 de dano) e seta de éter dos besteiros (22). Retorno usa trajetória visível/raycast até o emissor, respeita obstáculos e não fere colegas nem produz cadeia de reflexões. Guarda prolongada volta ao bloqueio normal; outros ataques/perigos não ganham reflexão automaticamente.

Teste isolado de 07/10 conferiu frente/costas, janela, cooldown, duplicação e retorno de 22 de dano a Humanoid de teste. Inspeção de código atual em 15/10 confirmou a função TentarRefletir e os limites. Não houve novo Play completo de parry nesta revisão documental; encaixe visual em combate real e multiplayer permanecem pendentes. Durabilidade e reparo continuam futuros.

## 6. Autômatos da Masmorra
Os dois lacaios de apoio da arena do Guardião (fora das salas comuns) usam um rig interno R15 nativo com o visual do golem comum aplicado sobre ele; o Guardião do Piso 1 usa o avatar R15 próprio do chefe. Ambos usam somente as animações R15 padrão do Roblox para espera, caminhada e corrida; não há marcha procedural. O rig interno mantém os lacaios firmes após o despertar, sem travar a animação.

- Os lacaios usam perseguição direta ou pathfinding, ataque por proximidade e velocidade normal de 13 studs/s.
- O lacaio alterna entre um soco fraco e um golpe concentrado. Antes de cada ataque, ele se orienta para o alvo. As duas animações funcionam sem arma nesta fase e poderão ser reutilizadas quando o armamento do autômato for criado.
- O Guardião é selecionado pelo gerador pelo prefab `Golem_Pedra`, antes do modelo antigo `Chefe`, e mantém IA própria, 450 pontos de vida, alcance e dano distintos.
- O Guardião do Piso 1 empunha uma clava fixada na mão direita. Seu ataque atual usa uma única animação de clava, sincronizada com a janela de dano do combate e orientada para o alvo antes do golpe.

## 7. Guarda da Entrada da Masmorra
Armand e Leofric são os guardas estáticos posicionados nas laterais da entrada do Mausoléu, sem bloquear o acesso ao portal. Ambos permanecem em espera com a animação R15 padrão do Roblox; Armand segura uma lança na mão direita e Leofric na mão esquerda. Não patrulham nem participam de combate.

- Interação: `E` para conversar.
- Avisos: a masmorra exige preparo, o Piso 1 exige preparo e o Guardião protege a passagem adiante. Autômatos Lacaios são apoio da arena, não o catálogo comum atual (GAME-010).

## 8. Mestre Cedric da Oficina
O Mestre Cedric usa um avatar R15 estático, escalado para manter a altura do avatar anterior e posicionado de frente para o balcão da oficina. Ele não patrulha e usa somente a animação padrão R15 de espera. Ao iniciar uma conversa, volta-se brevemente para o jogador e depois retorna à posição de trabalho.

- A interação de forja existente e o identificador de diálogo do Cedric são preservados.
- O nome não é exibido sobre a cabeça do personagem.
