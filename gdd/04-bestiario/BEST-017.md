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
  - "GAME-011"
  - "ITEM-008"
  - "ITEM-009"
  - "ITEM-010"
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
| Velocidade normal / recuperação | 8 / 4 studs/s |
| Preparação inicial / segunda | 0,8 / 0,38 s |
| Intervalo após a salva | 2,6–3,6 s |
| Recuperação / desestabilização por reflexão | 1,4 / 0,65 s |
| Distância pretendida normal / recuperação | 16 / 7 studs |
| Separação pretendida / limite mínimo | 8 / 5,5 studs |

Configuração em `PISO1_Vesplume.Config`; a vida vem do prefab. A oscilação visual acrescenta cerca de ±0,24 stud à altura. Asas, boca, voo e efeitos usam o controlador procedural existente.

## Estado e validação

Modelo, controle de voo, ataque, recuperação e spawn estão implementados, substituindo o estado apenas conceitual registrado em 05/10/2026. Play com espada real derrotou um, dois e três Vesplumes. Escudo, reflexão para o emissor e saída lateral foram verificados. A geração de 08/10 confirmou a coexistência com as quatro espécies terrestres.

Os testes automatizaram movimento e timing; não representam dificuldade definitiva, execução manual de dash/parry, multiplayer real ou revisão de toda geometria.

## Espólios implementados — 08/10/2026

**IMPLEMENTADO e TESTADO em Play local; validação final/multiplayer pendentes.**

| Espólio | Ficha | Raridade | Uso atual / destino futuro |
|---|---|---|---|
| Secreção Luminescente | ITEM-008 | Comum | Coleta/bolsa/informações; tratamento futuro para iluminação. |
| Membrana de Vesplume | ITEM-009 | Comum | Coleta/bolsa/informações; boticário/artesanato futuros. |
| Glândula Luminosa | ITEM-010 | Raro | Coleta/bolsa/informações; Guilda/receitas avançadas planejadas. |
| Cobre | GAME-011 | Moeda | Carteira existente, até 10 unidades por sorteio. |
| Prata | GAME-011 | Moeda | Mesma carteira, até 2; conversão provisória existente preservada. |

Sorteio único, vazio possível, resultado compartilhado, coleta parcial e ficha independente. Sem drops individuais no chão. Corpo inerte após derrota; afundamento após encerramento efetivo da sala/grupo.

GAME-011 registra chances, segurança, ciclo real, scripts/testes. Reabrir não sorteia. Refinar, vender, fabricar ou cumprir contratos continua futuro.

### Refinamento de combate vigente

Salva de dois disparos: aviso inicial 0,8 s; espera de 0,48 s e segunda preparação de 0,38 s. Travamento de mira 0,16 s antes do tiro, previsão limitada a 0,22 s/3 studs. Intervalo seguinte 2,6–3,6 s; recuperação 1,4 s; velocidade de recuperação 4 studs/s; desestabilização por reflexão 0,65 s. Substituem a tabela anterior de teste.

## Referência visual

> **Imagem publicada:** Vesplume, arte horizontal aprovada para o Bestiário.
> Arquivo: `./assets/bestiario/BEST-017.png`.

A ilustração é a referência visual da ficha; o modelo 3D do jogo permanece independente da arte do GDD.
