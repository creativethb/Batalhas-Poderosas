---
id: "GAME-010"
nome: "Encontros e combate do Piso 1"
funcao: "Sorteio, IA, dano e integração de baús"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "DNG-013"
  - "GAME-011"
  - "GAME-002"
  - "BEST-017"
  - "BEST-018"
  - "BEST-019"
  - "BEST-020"
  - "BEST-021"
  - "BEST-022"
imagem: ""
atualizado_por: "Codex"
data_atualizacao: "2026-10-08"
---

# Encontros e combate do Piso 1

## Estado da implementação — 08/10/2026

O gerador de salas permanece procedural. Seu adaptador de encontros está ativo apenas em Ruinas e PilaresArmadilha. O catálogo comum tem cinco espécies: Vesplume, Grumelo, Pedrino, Brisalto e Cascudo.

Baú Falso é encontro especial e não ocupa um sexto slot de espécie comum. Autômatos Lacaios não voltam ao catálogo comum: pertencem ao apoio do Guardião. Salas protegidas e arena mantêm seus fluxos específicos.

## Sorteio ordenado e reproduzível

`PISO1_EncontrosPlanejador` produz um plano sem instanciar objetos. Usa Seed e SalaId para reproduzir o sorteio, valida capacidade de sockets, espécies habilitadas, pesos e limites. Enumera combinações com repetição sem favorecer apenas a ordem de seleção; escolhe composição homogênea ou mista, distribui sockets distintos e aplica atrasos individuais.

| Parâmetro atual | Configuração provisória |
|---|---|
| Solo | 1 a 3 adversários; não há 4 ou 5 no sorteio solo atual |
| Peso de quantidade 1 / 2 / 3 | 10 / 55 / 35 |
| Peso homogênea / mista | 1 / 3 |
| Peso das espécies comuns | 1 para cada espécie habilitada |
| Atraso individual | 0,20–0,50 s |
| Tipos de encontro Combate / BauRecompensa / BauFalso | 92 / 8 / 0 |
| Catálogo comum | MaximoEspecies=5 |
| Limite absoluto preparado | 6; não equivale a dificuldade multiplayer aplicada |
| MaximoPorGrupo | vazio; sem regra específica definida por tamanho de grupo |

Uma composição pode repetir a mesma espécie ou misturar terrestres e aéreos. Não foram habilitadas raridades finais, salas vazias de recompensa aleatória nem escalonamento de dificuldade por grupo.

## Ativação e arquitetura

`DungeonSystemController` monta o piso e chama o adaptador nas salas permitidas. `PISO1_EncontrosSpawn` registra o encontro como ativado **antes de qualquer espera**, evitando duplicação quando jogadores entram juntos; consulta o planejador e chama as fábricas das espécies.

Quantidade e dificuldade para grupos permanecem pendentes: o código conta participantes e reserva MaximoPorGrupo, mas sem configuração específica utiliza o limite solo. Essa preparação não representa validação multiplayer.

Os módulos de espécie controlam território, aproximação, intervalos, preparação e recuperação. Os rigs e modelos preparados foram reutilizados; arte provisória poderá ser substituída sem refazer o circuito de encontro.

## Dano, defesa e animações

Ataques terrestres sincronizam consulta de contato ou área com o golpe. Usam `CombateDefesaService.AplicarDano`, preservando espada, guarda, esquiva e parry já existentes. A redução frontal do Cascudo é registrada apenas para seu Humanoid e removida ao encerrar.

Grumelo, Pedrino, Brisalto e Cascudo utilizam locomoção padrão R15 e poses de golpe em Motor6D.C0; Vesplume e Baú Falso usam seus controladores procedurais. Nenhum pacote exclusivo de animações foi publicado nesta etapa.

## Baús

O baú verdadeiro agora é instanciado sobre o altar das salas Bau por `PISO1_BauTesouro`, com a geometria apoiada na superfície. O controlador usa o C0 real da dobradiça escalada, abre/fecha, valida jogador vivo e próximo e recusa concorrência durante a animação.

`OnChestOpened` emite WorldCFrame do RewardSpawnPoint e jogador somente na primeira abertura concluída. Não concede recompensas e não repete o sinal ao reabrir. Abrir não registra coleta individual do grupo.

A fábrica BauRecompensa participa com peso 8 nas salas comuns; combate tem peso 92. No altar das salas Bau, uma única escolha determinística cria baú verdadeiro ou falso, com 12% provisórios para o falso. Não há sobreposição nem Vesplume elite adicional nessa sala. Ambos continuam sem loot; espólios desta etapa são exclusivos do Vesplume (GAME-011).

## Validação e limites

As espécies foram enfrentadas com a Tool real da Espada de Madeira em grupos de um, dois e três; impactos, bloqueios e recuperações foram testados individualmente. O planejador foi exercitado em 5.000 sementes, com 252 encontros de um, 2.803 de dois e 1.945 de três na amostra.

Na seed 8040801, seis salas mantiveram as quantidades planejadas e invocaram 3 Vesplumes, 2 Grumelos, 6 Pedrinos, 3 Brisaltos e 2 Cascudos. A geração/ativação do Guardião foi preservada. Baús tiveram teste de interação cliente-servidor, concorrência, distância e posicionamento.

Não houve teste real com vários clientes, combate completo do Guardião ou percurso completo do Piso 2 nesta rodada. Deslocamentos de esquiva foram controlados; timing automatizado de parry não mede facilidade manual. Acabamento estético, balanceamento, raridades, loot e economia continuam em desenvolvimento.

## Consolidação do refinamento e espólios — 08/10/2026

Máximo de duas repetições consecutivas da quantidade anterior. PISO1_CombateCoordenador coordena flancos/pressão/reserva de ataques terrestres, apresentação da invocação e barra de vida contextual. Vesplume usa salva de dois tiros, aviso e mira travada antes de disparar; BEST-017 contém valores atuais.

Registro anterior de 5.000 sementes descreve a configuração anterior. Refinamento posterior testou 2.000 planos: 209 de um, 893 de dois, 732 de três, 166 de recompensa; máximo de duas quantidades consecutivas iguais. Teste de 240 pontos dedicados de baú: 207 verdadeiros e 33 falsos, um por ponto.

GAME-011 acrescenta inspeção/espólios compartilhados exclusivamente do Vesplume, com materiais na bolsa e moedas na carteira existentes. Não altera a coordenação de combate, Guardião, baús ou Piso 2. Multiplayer real continua pendente.
