---
id: "BEST-017"
nome: "Vesplume"
funcao: "Aéreo de ataque à distância"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "DNG-013"
  - "GAME-010"
  - "GAME-002"
imagem: "./assets/bestiario/BEST-017.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-08"
---

# Vesplume

## Identidade

Criatura cavernícola voadora, de corpo mole e parcialmente translúcido, asas membranosas e bolsa orgânica de secreção luminosa e corrosiva. A bioluminescência é biológica, não manifestação de magia.

## Gameplay implementada

Espécie aérea comum do Piso 1, habilitada no sorteio com as quatro espécies terrestres. Posiciona-se → prepara disparo com aviso → expele secreção → recupera em voo baixo móvel → retoma.

Após disparar, desce gradualmente para permitir aproximação pela Espada de Madeira, mantendo evasão reduzida. Não fica imóvel aguardando dano. Separação lateral e intervalos individuais evitam aglomeração e sincronização contínua.

O projétil causa 12 de dano pelo serviço existente, pode ser bloqueado e pode ser refletido pelo parry já implementado. Reflexão que atinge o emissor provoca breve desestabilização e recuperação.

| Configuração provisória | Valor |
|---|---:|
| Vida observada nos testes do prefab | 90 |
| Altura normal / recuperação | 5,5 / 3,4 studs acima do piso |
| Velocidade normal / recuperação | 8 / 3 studs/s |
| Preparação do disparo | 0,9 s |
| Intervalo configurado | 3,6–4,7 s, acrescido do aviso e seleção de posição |
| Recuperação / desestabilização por reflexão | 2,8 / 0,5 s |
| Distância pretendida normal / recuperação | 16 / 7 studs |
| Separação pretendida / limite mínimo | 8 / 5,5 studs |

Configuração em `PISO1_Vesplume.Config`; a vida vem do prefab. A oscilação visual acrescenta cerca de ±0,24 stud à altura. Asas, boca, voo e efeitos usam o controlador procedural existente.

## Estado e validação

Modelo, controle de voo, ataque, recuperação e spawn estão implementados, substituindo o estado apenas conceitual registrado em 05/10/2026. Play com espada real derrotou um, dois e três Vesplumes. Escudo, reflexão para o emissor e saída lateral foram verificados. A geração de 08/10 confirmou a coexistência com as quatro espécies terrestres.

Os testes automatizaram movimento e timing; não representam dificuldade definitiva, execução manual de dash/parry, multiplayer real ou revisão de toda geometria.

## Espólio e integração futura

A secreção bioluminescente permanece como possível recurso futuro para a cadeia dos Frascos Luminosos, após tratamento/refinamento. Nome do recurso, probabilidades, quantidades e integração com Guilda/economia não estão definidos. Não há loot implementado para esta espécie nesta etapa.

## Referência visual reservada

> **Imagem pendente:** Vesplume.
> Arquivo reservado: `./assets/bestiario/BEST-017.png`.

O modelo atual é provisório. A imagem definitiva será anexada depois; não foi criada uma imagem fictícia nesta atualização.
