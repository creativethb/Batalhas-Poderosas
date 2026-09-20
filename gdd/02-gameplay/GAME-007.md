---
id: "GAME-007"
nome: "Navegação da Vila e Mapa do Diário"
status: "EM_DESENVOLVIMENTO"
relacionados:
  - "GAME-005"
  - "ITEM-004"
  - "LOCAL-001"
  - "LOCAL-002"
  - "LOCAL-003"
  - "LOCAL-004"
  - "LOCAL-005"
  - "LOCAL-006"
atualizado_por: "codex"
data_atualizacao: "2026-09-20"
---

# Navegação da Vila e Mapa do Diário

O sistema de navegação orienta John pela Vila de Arkham sem substituir a exploração. O mapa é consultado no Diário de John; durante o percurso, uma microbússola discreta indica somente a direção do destino marcado.

---

## 1. Fluxo de Uso

1. John abre o Diário.
2. Seleciona **Mapa da Vila**.
3. O mapa abre em tela cheia como uma representação ilustrada, fiel à topologia da vila.
4. John arrasta para explorar e usa os controles de zoom quando necessário.
5. Seleciona um local conhecido.
6. O mapa e o Diário fecham automaticamente; a microbússola passa a indicar o caminho.

O sistema marca um destino; ele não teleporta o jogador nem mostra uma rota obrigatória.

---

## 2. Estado de Desenvolvimento

Durante o desenvolvimento, o mapa fica disponível diretamente para permitir validação da navegação da vila. A implementação usa uma arte topográfica própria da Vila de Arkham, com marcadores presos às posições equivalentes dos locais reais.

A primeira versão contém destinos reais da vila, incluindo Casa de John, Mercado Central, Oficina de Cedric, Padaria, Taverna do Javali Dourado, Guilda, Estábulo, Serraria, Moinho, Igreja, Santuário de Eldrin e Paço Municipal.

O mapa abre com a vila inteira visível e preserva zoom e arrasto em computador e mobile. A arte está quadrada nesta fase de desenvolvimento; o enquadramento final horizontal poderá ser refinado junto da HUD definitiva.

---

## 3. Progressão Canônica Planejada

John inicia a jornada sem acesso ao Mapa da Vila. Em um ponto narrativo futuro, ele encontrará ou receberá o item **Mapa da Vila**, que será integrado ao Diário de John.

Após a aquisição:

- a página de mapa será liberada;
- áreas ainda não descobertas poderão aparecer como interrogações;
- ao chegar a uma área, seu ícone e nome reais serão revelados;
- somente locais já descobertos por John deverão aparecer como destinos;
- a microbússola será ativada apenas após a seleção de um destino disponível.

O desbloqueio técnico previsto usa o estado `MapaDaVilaDesbloqueado` no jogador. O evento narrativo de aquisição, seu responsável e o momento da campanha permanecem a definir.

---

## 4. Diretrizes de Experiência

- O mapa oferece orientação sem eliminar a necessidade de explorar.
- A microbússola ocupa pouco espaço e mostra somente uma seta direcional; ela some ao chegar próximo ao destino.
- O Diário é a fonte central de consulta e preserva seu papel narrativo e funcional.
- A expansão da vila deve acrescentar novos destinos ao catálogo de navegação junto com a documentação correspondente.
- A imagem do mapa e a posição dos marcadores devem ser atualizadas juntas quando a topologia da vila mudar.

---

## 5. Validação Atual

Em playtest de desenvolvimento:

- o Diário abriu o Mapa da Vila;
- o mapa topográfico exibiu os 12 marcadores de destino;
- o zoom foi validado em computador;
- no simulador de iPhone em paisagem, a vila abriu inteiramente visível;
- ao selecionar o Mercado Central, o mapa e o Diário fecharam e a microbússola foi ativada.

