---
id: "GAME-007"
nome: "Navegação da Vila e Mapa Independente"
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
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Navegação da Vila e Mapa Independente

O mapa e o diário são interfaces separadas. A bússola existente aponta para destinos reais e objetivos da missão, sem teletransportar o jogador.

## 1. Acesso atual

- `mapa_arkham`: item único, não empilhável e persistente no inventário existente; `UseMode="AbrirMapa"`.
- O atalho M e o acesso de interface dependem da posse. Não há concessão automática nesta etapa.
- Selecionar um destino fecha o mapa e ativa a microbússola existente. Zoom, arrasto e lista de destinos reutilizam NavegacaoVilaClientV2.
- A bússola de missão **não depende da posse do mapa**: Cedric → igreja → árvore/retorno ao padre → Eldrin seguem os objetivos da campanha.
- A interface independente substitui a janela anterior por BP_UIState. Não exige abrir o diário nem uma categoria da bolsa.

## 2. Geografia e destinos

A arte topográfica e os destinos existentes foram preservados: casa, mercado, oficina, padaria, taverna, guilda, estábulo, serraria, moinho, igreja, santuário e Paço. A conferência cartográfica fina continua necessária quando houver alteração da vila. Referências de destino devem usar a posição real, não coordenadas antigas copiadas das fichas.

## 3. Planejamento ainda aberto

A forma e o momento de aquisição do mapa não foram definidos. Descoberta gradual de áreas, interrogações e filtragem por locais descobertos são planejamento; não inferir que já funcionam. O antigo estado proposto `MapaDaVilaDesbloqueado` não substitui a verificação de posse do item implementado.

## 4. Testes e limites

Play de 13/10: sem posse, M não abriu o mapa e o acesso ficou oculto; após aquisição temporária pelo serviço existente, abriu independentemente. Selecionar Cedric encerrou o mapa e ativou a bússola. Exportação e recarga em memória mantiveram mapa/diário sem criar outra carteira. Arte, zoom e destinos já tinham testes locais anteriores em PC/simulador mobile. Controle Y/B foi mapeado anteriormente, mas validação com controle físico permanece pendente. Não houve nova reconexão real entre servidores.
