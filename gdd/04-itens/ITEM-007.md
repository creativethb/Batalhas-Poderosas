---
id: "ITEM-007"
nome: "Escudo de Madeira"
funcao: "Equipamento inicial de defesa frontal"
status: "CANONICO"
localizacao: "Oficina de Mestre Cedric / inventário de John"
relacionados:
  - "NPC-001"
  - "LOCAL-002"
  - "ITEM-003"
  - "GAME-001"
  - "GAME-002"
  - "GAME-003"
  - "GAME-009"
imagem: "./assets/itens/ITEM-007.png"
atualizado_por: "codex"
data_atualizacao: "2026-10-06"
---

# Escudo de Madeira

## Definição e origem

- **ID de runtime:** `escudo_madeira`.
- **Tipo:** equipamento defensivo de mão secundária.
- **Raridade:** Comum.
- **Natureza:** proteção física artesanal, sem efeito mágico.
- **Representação:** madeira, aro de ferro, pega e correia no verso.
- **Quantidade:** item único, não empilhável; máximo de uma unidade.

Mestre Cedric entrega o escudo **como cortesia junto à primeira espada**, uma única vez por personagem. A entrega não cobra moeda, não exige materiais extras e não altera a receita da espada. O diálogo da entrega explica a cortesia; a opção posterior **“Sobre o Escudo de Madeira.”** permite retomar essa explicação sem conceder outra unidade.

A origem material dos componentes da peça pronta não cria uma nova receita ou cadeia de coleta nesta etapa.

## Circuito de gameplay

`Materiais da espada → primeira forja com Cedric → espada + escudo de cortesia → inventário → equipar no braço esquerdo → levantar guarda → bloquear ataques frontais → soltar e retomar ações`

O encaixe e o tamanho foram ajustados manualmente pelo responsável e preservados nesta implementação. O escudo usa o slot `MaoSecundaria`; a espada continua na mão direita. Desequipar remove apenas a representação equipada, mantendo o item no inventário.

A revisão narrativa com Madeira Ungida em **GAME-001** permanece pendente; a integração do escudo não implementa essa revisão nem substitui a obtenção atual dos materiais.

## Defesa básica implementada

- **Ativar/manter:** segurar botão direito do mouse ou `C` no PC; manter o botão **Defesa** existente no celular. `ButtonL2` foi mapeado para controle.
- **Encerrar:** soltar. Desequipar, morrer, iniciar diálogo/menu ou entrar em estado incompatível também encerra a guarda.
- **Condição:** possuir e estar com o escudo válido equipado.
- **Proteção:** bloqueio integral de ataques comuns bloqueáveis dentro de um arco frontal de **120°** (±60°). Costas e laterais fora do arco recebem dano normal.
- **Movimento:** caminhada reduzida de 16 para **10 studs/s**.
- **Prioridade:** espada, dash, corrida, segundo pulo e animações manuais de sacar/guardar ficam impedidos durante a defesa. Uma ação incompatível já em execução impede iniciar a guarda.
- **Feedback:** breve recuo do braço e som físico discreto; sem magia, barra ou nova interface.
- **Autoridade:** o servidor verifica item, slot, visual fixado ao braço, vida, estados incompatíveis e direção do ataque. A pose visual isolada não concede proteção.

A postura é uma animação procedural das juntas esquerdas, aplicada após o Animator, com entrada de 0,18 s e saída de 0,22 s. Preserva pernas e braço direito; funciona no rig atual de John com `AnimationConstraint` e possui adaptação para `Motor6D`. A prioridade é resolvida pela camada de pose e pela exclusão das ações incompatíveis; não depende de ID temporário de animação do Studio.

## Persistência e integração técnica

Inventário e equipamento usam a persistência existente. O registro `Fase1_EscudoCortesiaRecebido` / `ProgressoFase1.EscudoCortesiaRecebido` impede repetição da cortesia.

Ataques comuns consultam `CombateDefesaService.AplicarDano`, informando sua origem no servidor. A interface admite `Bloqueavel=false` e `QuebraGuarda=true` como pontos de extensão; nenhum ataque novo de quebra de guarda foi criado.

Armadilhas, dano ambiental e efeitos de área mantêm as regras anteriores. A secreção do Vesplume é interceptada sem reflexão.

## Estado e validação — 06/10/2026

**Implementado e TESTADO em Play local**, com perfil de teste separado da persistência de produção.

Verificados: postura com espada/escudo; segurar/soltar em PC; botão móvel com toque mantido no simulador de iPhone 17 Pro em paisagem; caminhar defendendo; bloqueio frontal; dano lateral e traseiro; desequipar/requipar; conflitos com espada/dash/corrida; retorno às ações normais; morte/renascimento; bolsa e interrupção de diálogo; rejeição de guarda falsificada apenas no cliente.

Combate real conferido com Lacaio, golpe do Guardião e projétil do Vesplume. O Vesplume foi testado em arena temporária isolada de Play, sem mudar a progressão da dungeon. A execução final não apresentou erros de runtime no Output.

Controle/gamepad físico, telefone físico, multiplayer e travessia completa das rotas do Piso 2 **não foram testados nesta etapa**. O mapeamento `ButtonL2` e a apresentação da postura para outros jogadores estão preparados, sem declarar validação desses ambientes.

## Fora desta etapa

Parry, defesa perfeita, reflexão, durabilidade, desgaste, escudo quebrado, reparos, compra, melhorias e variações permanecem futuros. Não foram criados loot, itens adicionais ou economia.
