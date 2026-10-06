---
id: "GAME-002"
nome: "Sistema de Combate e Combos"
status: "CANONICO"
relacionados:
  - "ITEM-007"
  - "ITEM-003"
  - "GAME-001"
  - "BP-2026-005"
atualizado_por: "codex"
data_atualizacao: "2026-10-06"
---

# Sistema de Combate e Combos de Espada

## 1. Referência Documental de Golpes (Combo de 5 Hits — validação pendente)
> 🔎 **Auditoria documental (22/09/2026):** os cinco golpes abaixo são a especificação registrada neste arquivo. Não há documento independente que confirme que este seja o número atualmente implementado. A contagem, IDs, tempos e comportamento real devem ser validados no Roblox Studio antes de serem tratados como estado de runtime.

A especificação registrada descreve uma sequência encadeada de 5 animações na prioridade `Action`:
- **Hit 1:** `rbxassetid://132874711732733`
- **Hit 2:** `rbxassetid://102975027054676`
- **Hit 3:** `rbxassetid://129511831949775`
- **Hit 4:** `rbxassetid://93640942970410`
- **Hit 5:** `rbxassetid://96266670191454`

## 2. Regras de Encadeamento & Reset
- Cada ativação avança para o golpe seguinte (`1 → 2 → 3 → 4 → 5 → 1`).
- **Cooldown entre Golpes:** `0.42s`.
- **Tempo de Reset de Combo:** `1.15s` de inatividade reinicia o ciclo no Hit 1.
- **Impulso Tático:** Golpes desferidos em repouso geram um leve avanço frontal no personagem.

## 3. Hitbox & Validação de Dano
- **Detecção Espacial:** Varredura em tempo real (`GetPartBoundsInBox`) em torno da lâmina durante a janela ativa do golpe (0.28s).
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
- **Animação:** sobreposição procedural apenas nas juntas esquerdas, após o Animator, com entrada de 0,18 s e saída de 0,22 s. Preserva pernas e braço direito e suporta AnimationConstraint do John atual e Motor6D. A prioridade é resolvida pela camada de pose e pela exclusão das ações incompatíveis, sem ID temporário de animação.
- **Impacto:** pequeno recuo e som físico discreto, sem magia ou indicadores novos.

O GerenciadorCombateServer mantém o remote de dano existente e coordena solicitações de guarda/ação. A regra comum reside em SistemasGameplay.CombateDefesaService: estado autoritativo, equipamento e AplicarDano. Cada ataque comum informa sua origem no servidor; IA, alcance, cadência e progressão são preservados. Bloqueavel=false permite ignorar a guarda; QuebraGuarda=true permanece ponto de extensão, sem ataque novo criado. Armadilhas e efeitos de área mantêm o comportamento anterior.

A configuração de espada encontrada no código mantém três animações, cooldown de 0,38 s e reset de 1,15 s. A referência anterior de cinco golpes nas seções 1–2 permanece identificada como especificação com validação pendente; esta tarefa não migra o combo.

**Playtest realizado:** C/mouse direito; toque mantido no botão móvel no simulador de iPhone 17 Pro em paisagem; segurar/soltar; caminhada; frente/costas/lateral; ataque marcado como não bloqueável; Lacaio, golpe do Guardião e ácido do Vesplume reais; desequipar/requipar; conflitos com espada/dash/corrida; morte/renascimento; bolsa e interrupção de diálogo; rejeição de pose falsificada no cliente. O Play final não apresentou erros de runtime. Não houve teste de telefone/controle físicos, multiplayer ou progressão completa do Piso 2.

Parry, reflexão, durabilidade, reparo, variantes e compra permanecem fora desta etapa.

## 6. Autômatos da Masmorra
Os lacaios do primeiro piso usam um rig interno R15 nativo com o visual do golem comum aplicado sobre ele; o Guardião do Piso 1 usa o avatar R15 próprio do chefe. Ambos usam somente as animações R15 padrão do Roblox para espera, caminhada e corrida; não há marcha procedural. O rig interno mantém os lacaios firmes após o despertar, sem travar a animação.

- Os lacaios usam perseguição direta ou pathfinding, ataque por proximidade e velocidade normal de 13 studs/s.
- O lacaio alterna entre um soco fraco e um golpe concentrado. Antes de cada ataque, ele se orienta para o alvo. As duas animações funcionam sem arma nesta fase e poderão ser reutilizadas quando o armamento do autômato for criado.
- O Guardião é selecionado pelo gerador pelo prefab `Golem_Pedra`, antes do modelo antigo `Chefe`, e mantém IA própria, 450 pontos de vida, alcance e dano distintos.
- O Guardião do Piso 1 empunha uma clava fixada na mão direita. Seu ataque atual usa uma única animação de clava, sincronizada com a janela de dano do combate e orientada para o alvo antes do golpe.

## 7. Guarda da Entrada da Masmorra
Armand e Leofric são os guardas estáticos posicionados nas laterais da entrada do Mausoléu, sem bloquear o acesso ao portal. Ambos permanecem em espera com a animação R15 padrão do Roblox; Armand segura uma lança na mão direita e Leofric na mão esquerda. Não patrulham nem participam de combate.

- Interação: `E` para conversar.
- Avisos: a masmorra exige preparo, os autômatos patrulham o primeiro piso e o Guardião protege a passagem adiante.

## 8. Mestre Cedric da Oficina
O Mestre Cedric usa um avatar R15 estático, escalado para manter a altura do avatar anterior e posicionado de frente para o balcão da oficina. Ele não patrulha e usa somente a animação padrão R15 de espera. Ao iniciar uma conversa, volta-se brevemente para o jogador e depois retorna à posição de trabalho.

- A interação de forja existente e o identificador de diálogo do Cedric são preservados.
- O nome não é exibido sobre a cabeça do personagem.
