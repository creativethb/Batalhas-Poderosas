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

O sistema de navegação orienta John pela Vila de Arkham sem substituir a exploração. O mapa é consultado no Diário de John; a orientação durante o percurso é feita por uma bússola discreta na interface.

---

## 1. Fluxo de Uso

1. John abre o Diário.
2. Seleciona **Mapa da Vila**.
3. Escolhe um local conhecido no mapa ou na lista de destinos.
4. O mapa fecha e a bússola passa a indicar a direção e a distância até o destino marcado.

O sistema marca um destino; ele não teleporta o jogador nem mostra uma rota obrigatória.

---

## 2. Estado de Desenvolvimento

Durante o desenvolvimento, o mapa fica disponível diretamente para permitir validação da navegação da vila. A primeira versão contém destinos reais da vila, incluindo Casa de John, Mercado Central, Oficina de Cedric, Padaria, Taverna do Javali Dourado, Guilda, Estábulo, Serraria, Moinho, Igreja, Santuário de Eldrin e Paço Municipal.

---

## 3. Progressão Canônica Planejada

John inicia a jornada sem acesso ao Mapa da Vila. Em um ponto narrativo futuro, ele encontrará ou receberá o item **Mapa da Vila**, que será integrado ao Diário de John.

Após a aquisição:

- a página de mapa será liberada;
- somente locais já descobertos por John deverão aparecer como destinos;
- a bússola será ativada apenas após a seleção de um destino disponível.

O desbloqueio técnico previsto usa o estado `MapaDaVilaDesbloqueado` no jogador. O evento narrativo de aquisição, seu responsável e o momento da campanha permanecem a definir.

---

## 4. Diretrizes de Experiência

- O mapa oferece orientação, sem eliminar a necessidade de explorar.
- A bússola deve ocupar pouco espaço e mostrar somente destino, direção e distância.
- O Diário é a fonte central de consulta e preserva seu papel narrativo e funcional.
- A expansão da vila deve acrescentar novos destinos ao catálogo de navegação junto com a documentação correspondente.

---

## 5. Validação Atual

Em playtest de desenvolvimento, o Diário abriu a página de mapa; o Mercado Central foi selecionado; e a bússola exibiu corretamente a direção e a distância até o destino.

