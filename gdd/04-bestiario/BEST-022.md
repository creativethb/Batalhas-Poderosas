---
id: "BEST-022"
nome: "Baú Falso"
funcao: "Encontro especial disfarçado de baú"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1 / altar dedicado de baú"
relacionados:
  - "DNG-013"
  - "GAME-010"
  - "DNG-002"
imagem: "./assets/bestiario/BEST-022.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Baú Falso

## Classificação e apresentação

Encontro especial do Piso 1, separado das cinco espécies comuns. Usa o modelo `BauFalso` e a transformação já preparados, preservando 48 peças e 15 Motor6D.

Inicialmente fechado e imóvel, com membros/olhos ocultos, sem nome, barra de vida ou alvo de foco. Não persegue John e não concede recompensas na interação.

## Revelação

Interação de abrir → tremor da tampa → abertura e olhos → desdobramento dos braços e pernas → elevação → breve reconhecimento → combate.

A transformação ocorre uma única vez por encontro, com trava anterior às esperas; solicitações simultâneas são recusadas. O prompt é desativado. O modelo não é substituído e não há duplicação de peças. Dano durante a revelação é aceito; morte nessa fase interrompe a sequência.

## Combate

Observar → aproximar moderadamente → preparar → atacar → recuperar → recuar/reposicionar, com pequenos saltos ocasionais.

**Mordida de Tampa:** abre com preparação clara e fecha rapidamente. O dano consulta a própria tampa somente durante o fechamento, à frente, com limite de alcance e checagem de parede. Errar deixa a tampa aberta para contra-ataque.

**Investida Saltitante:** flexiona as pernas e dá salto curto. A direção é capturada na impulsão e não segue John no ar. Dano usa contato do corpo durante o impacto; paredes impedem/interrompem o movimento. Errar exige recuperação mais longa.

| Configuração provisória | Valor |
|---|---:|
| Vida | 110 |
| Aproximação / lateral | 9 / 4 studs/s |
| Mordida / investida | 12 / 16 de dano |
| Preparação mordida / investida | 0,65 / 0,85 s |
| Fechamento da tampa | 0,18 s |
| Reconhecimento após levantar | 1,1 s |
| Recuperação de acerto | 0,75 s |
| Recuperação mordida errada / investida errada | 1,25 / 1,5 s |
| Intervalo após o ciclo | 2,2–3,3 s |
| Investida máxima / duração prevista | 4,5 studs / 0,36 s |

Parâmetros em `PISO1_BauFalso.Config`. Os ataques usam o serviço existente de dano e bloqueio. Recebe dano normalmente, sem criar parry, invulnerabilidade ou retirada de itens de John.

## Derrota e animações

Derrota interrompe IA, movimento, animação de caminhada, consultas ofensivas e prompt; o corpo perde equilíbrio e permanece inativo. Marca `EncontroConcluido` e emite `EncontroEncerrado`, com registro de espólios por inspeção após a derrota do baú revelado.

Todas as animações são procedurais nos motores existentes: transformação, respiração, caminhada alternada, tampa, flexão das pernas e queda. Não foram publicados novos IDs.

## Integração atual e futura

> **Espólios implementados provisoriamente em 11/10/2026:** ITEM-023 a ITEM-025, por inspeção compartilhada de GAME-011; detalhes abaixo.



O seletor PISO1_EncontrosSpawn.CriarBau usa um único ponto no altar das salas Bau. Uma escolha determinística por sessão/sala cria o verdadeiro ou o falso, com verificação de baú existente antes de instanciar. O original está reservado em ServerStorage; o prefab funcional fica em Dungeon_NPCs. A arena do Guardião e o catálogo de cinco inimigos comuns permanecem separados.

O refinamento habilitou `ProceduralAtivo=true` e `FrequenciaProcedural=0.35`, valores provisórios aplicados às salas com baú. `GarantirFalsoAteBau=2` força um falso até o segundo baú gerado caso o primeiro tenha sido verdadeiro. `ModoTesteStudio=false` desativa o ponto de teste adicional, evitando sobreposição. O peso BauFalso do sorteio de salas comuns continua zero; isso não desativa o seletor do altar. O Baú Falso concede materiais por inspeção após a derrota; a premiação do verdadeiro segue seu controlador próprio.

## Validação e pendências

Interação real, foco oculto/revelado, trava concorrente, 48 peças mantidas, dano e morte na transformação verificados. Mordida de 12, investida de 16, bloqueio, saída lateral, trajetória fixa, parede e recuperações testados. John venceu com cinco golpes reais de 22 da Espada de Madeira; após a morte, não houve novos ataques nem peças com colisão/consulta ativa.

Multiplayer real, frequência final, economia e revisão artística definitiva permanecem pendentes. Saídas laterais foram controladas pelo teste, sem acionar o comando real de dash.

## Referência visual reservada

> **Imagem pendente:** Baú Falso.
> Arquivo reservado: `./assets/bestiario/BEST-022.png`.

O modelo atual é provisório. A imagem definitiva será anexada depois; não foi criada uma imagem fictícia nesta atualização.


## Espólios do Baú Falso — 11/10/2026

Autorizados nesta data e implementados no Studio pelo sistema existente. ITEM-023 (dente_bau_falso): 55%, 1–2; ITEM-024 (dobradica_retorcida): 45%, 1; ITEM-025 (fechadura_viva): 8%, 1. Valores provisórios centralizados em EspoliosConfig. 20% de vazio forçado; nos demais casos, entradas independentes. Vazio total teórico 38,216%. Sem moedas, venda, preço ou receitas.

Após a derrota do baú revelado, ControladorBauFalso registra o corpo em EspoliosService. Morte durante a revelação também permite inspeção; derrotar o disfarce intacto por modo dev não concede materiais. Sorteio único, coleta seletiva compartilhada, alforge e persistência existentes preservados. Miniaturas nativas e informações compartilhadas em BP_ItemInterface/BancoDeItens.

Testado em Play local: transformação, morte, inspeção com três materiais, miniaturas, coleta parcial/integral, pedidos repetidos e excesso rejeitados, saque vazio e exportação do inventário. 10.000 sorteios verificaram limites. Não houve multiplayer real ou reconexão entre servidores. Estado IMPLEMENTADO / TESTADO localmente, sem marcar VALIDADO. Place não publicado nesta tarefa.
