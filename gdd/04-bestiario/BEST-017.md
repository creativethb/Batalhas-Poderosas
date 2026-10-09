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

## Espólios planejados e integração futura

> **Estado: PLANEJAMENTO APROVADO PARA DOCUMENTAÇÃO, NÃO IMPLEMENTADO.** Os nomes e funções iniciais abaixo foram aceitos como ponto de partida. Raridades propostas, chances, quantidades, preços, receitas e contratos ainda dependem de balanceamento/validação. Não converter sugestões de uso futuro em receitas canônicas.

| Espólio | Raridade proposta | Descrição breve para inspeção | Finalidade e destinos previstos |
|---|---|---|---|
| Secreção Luminescente | Comum | Líquido bioluminescente extraído da criatura. | Recurso biológico a tratar/refinar para a cadeia dos Frascos Luminosos; potencial abastecimento de iluminação de John. |
| Membrana de Vesplume | Comum | Membrana leve e flexível das asas. | Material possível para boticário ou artesão; receita específica não definida. |
| Glândula Luminosa | Raro | Órgão responsável pela produção da secreção luminosa. | Componente de interesse comercial da Guilda, com possíveis contratos e usos avançados em iluminação/alquimia, ainda não definidos. |
| Moeda de Cobre | Moeda, sem raridade de espólio | Moeda corrente encontrada entre os espólios. | Uso direto na economia da vila. |
| Moeda de Prata | Moeda, sem raridade de espólio | Moeda corrente de maior valor. | Uso direto na economia da vila; chance e quantidade devem respeitar o custo de produtos básicos, como o pão. |

### Inspeção, coleta e informações

- Ao derrotar o Vesplume, o sorteio de espólios acontece **uma única vez** e fica associado ao corpo; reabrir a inspeção não sorteia novamente.
- O corpo permanece após a animação de derrota. Ao aproximar-se, o jogador pode usar **Inspecionar**, com animação própria de John, para abrir uma janela compacta de espólios.
- A janela mostra itens efetivamente sorteados, quantidades, raridade quando aplicável, descrição curta e opção de **recolher individualmente** ou deixar no corpo.
- A ação **Informações** apresenta uma ficha mais completa: identidade, origem, propriedades, utilidades atuais e usos futuros claramente rotulados como planejados, além de possíveis destinatários comerciais.
- Itens não recolhidos continuam no mesmo corpo enquanto ele estiver disponível. Ao sair da sala, o corpo é removido com efeito de afundar/ser puxado pela terra; espólios restantes deixam de estar disponíveis.
- Coleta, inventário e eventual venda devem ser validados no servidor para impedir duplicação. Implementação e regras de multiplayer ainda precisam ser especificadas.
- As moedas são possibilidades adicionais, não substituem os três materiais. **Probabilidades, quantidades e valores de venda permanecem a definir.**

### Cadeias previstas

`Vesplume → inspeção → material/moedas → inventário → iluminação, boticário, artesão, Guilda ou comércio → uso/venda/entrega futura`

Cada material deverá possuir ficha própria `ITEM-XXX` em `gdd/04-itens/` conforme o padrão do GAME-009, com informações curta/completa e imagem reservada, após verificar a numeração disponível. Nenhuma receita ou estabelecimento novo é criado por esta ficha.

## Referência visual

> **Imagem publicada:** Vesplume, arte horizontal aprovada para o Bestiário.
> Arquivo: `./assets/bestiario/BEST-017.png`.

A ilustração é a referência visual da ficha; o modelo 3D do jogo permanece independente da arte do GDD.
