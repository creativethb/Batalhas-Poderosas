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
data_atualizacao: "2026-09-22"
---

# Navegação da Vila e Mapa do Diário

O sistema de navegação orienta John pela Vila de Arkham sem substituir a exploração. O mapa é consultado no Diário de John ou aberto diretamente pelo atalho de teclado durante o desenvolvimento. Durante o percurso, uma microbússola discreta indica somente a direção do destino marcado.

---

## 1. Fluxo de Uso

1. John abre o Diário.
2. Seleciona **Mapa da Vila**.
3. O mapa horizontal abre em tela cheia como uma representação ilustrada da vila.
4. John arrasta para explorar e usa os controles de zoom quando necessário.
5. Seleciona um local pelo marcador na arte ou pela lista com nomes, que também funciona em telas pequenas.
6. O mapa e o Diário fecham automaticamente; uma microbússola com ponteiro dourado em relevo passa a indicar o caminho.
7. Ao tocar ou clicar na microbússola, John pode **parar a orientação** ou **abrir o mapa** para escolher outro destino. No controle, o botão Y abre essas opções e B as fecha. Ao chegar perto do destino, a orientação é encerrada.

No computador, o atalho **M** abre e fecha o mapa diretamente. A aba **Mapa da Vila** continua disponível no Diário para computador e mobile.

O sistema marca um destino; ele não teleporta o jogador nem mostra uma rota obrigatória.

---

## 2. Estado de Desenvolvimento

Durante o desenvolvimento, o mapa fica disponível diretamente para permitir validação da navegação da vila. A implementação usa uma arte horizontal própria da Vila de Arkham, com marcadores ligados aos destinos reais. A arte é uma interpretação visual em desenvolvimento; a conferência cartográfica fina com a topologia final do mundo ainda é necessária.

A primeira versão contém destinos reais da vila, incluindo Casa de John, Mercado Central, Oficina de Cedric, Padaria, Taverna do Javali Dourado, Guilda, Estábulo, Serraria, Moinho, Igreja, Santuário de Eldrin e Paço Municipal.

O mapa abre com a vila inteira visível e preserva zoom e arrasto em computador e mobile. A tela combina arte, marcadores menores com área de toque preservada e uma lista rolável de destinos por nome. A lista de jogadores do Roblox fica oculta somente enquanto o mapa está aberto, para liberar a área de leitura.

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
- A microbússola ocupa pouco espaço e mostra somente um ponteiro dourado de aparência tridimensional; ela some ao chegar próximo ao destino.
- O Diário é a fonte central de consulta e preserva seu papel narrativo e funcional.
- A expansão da vila deve acrescentar novos destinos ao catálogo de navegação junto com a documentação correspondente.
- A imagem do mapa e a posição dos marcadores devem ser atualizadas juntas quando a topologia da vila mudar.

---

## 5. Validação Atual

Em playtest de desenvolvimento:

- o Diário abriu o Mapa da Vila;
- o mapa topográfico exibiu os 12 marcadores de destino;
- o zoom foi validado em computador;
- no simulador de iPhone em paisagem, a arte horizontal, os marcadores e a lista de destinos couberam na tela;
- ao selecionar o Mercado Central pelo nome, o mapa e o Diário fecharam e a microbússola foi ativada;
- o atalho M abriu o mapa diretamente no computador e a sobreposição da lista de jogadores foi removida.


---

## 6. Ajuste de controle da microbússola

O menu de opções fica associado à própria microbússola, sem botão permanente adicional na HUD. Parar a orientação limpa o destino ativo e oculta o indicador. O acesso por toque e mouse, assim como o encerramento da orientação, foi conferido em Playtest no computador em 2026-09-22. O mapeamento Y/B foi implementado para controle, mas ainda requer validação com um controle físico.
