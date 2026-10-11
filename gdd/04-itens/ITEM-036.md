---
id: "ITEM-036"
nome: "Candelabro de Expedição"
funcao: "Recompensa proposta do Piso 1"
tipo: "Equipamento utilitário / iluminação portátil"
raridade: "Raro"
status: "PLANEJADO"
localizacao: "Masmorra — Piso 1 (proposta)"
relacionados:
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
  - "ITEM-032"
  - "NPC-001"
  - "DOS-001"
  - "BEST-002"
imagem: "./assets/itens/ITEM-036.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Candelabro de Expedição

> **PROPOSTA DOCUMENTAL APROVADA PARA ESTA ETAPA.** Identidade, função pretendida e raridade provisória vêm da solicitação de 11/10/2026. Não é cadastro funcional de inventário, drop ativo, serviço disponível ou validação canônica definitiva. História e aspectos não confirmados permanecem indicados como propostas.

## Identificação e aparência

- **ID:** ITEM-036; **coleção:** Guardião Ancestral.
- **Categoria:** Equipamento utilitário / iluminação portátil.
- **Raridade proposta:** Raro; não determina uma probabilidade de drop.
- **Nome para o futuro inventário:** Candelabro de Expedição.
- **ID de runtime:** não cadastrado; será definido na futura integração.
- **Aparência:** Candelabro compacto com base estável e suporte metálico para transporte. O desenho de fontes de luz na miniatura é conceitual; não estabelece combustível, duração ou alcance.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Candelabro portátil de metal, pensado para iluminar câmaras e passagens.

**Descrição detalhada:** Candelabro compacto com base estável e suporte metálico para transporte. O desenho de fontes de luz na miniatura é conceitual; não estabelece combustível, duração ou alcance. Utilitário proposto para expedições prolongadas. Criador e antiga expedição não definidos. Sem origem mágica ou ancestral especial confirmada.

## História, origem e limites narrativos

Utilitário proposto para expedições prolongadas. Criador e antiga expedição não definidos. Sem origem mágica ou ancestral especial confirmada.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção proposta

Planejado para o conjunto de **espólios do Guardião Ancestral do Piso 1**, identificado no Bestiário como BEST-002 — Autômato de Pedra / Guardião. Guardião Ancestral é a denominação usada nesta proposta, não uma nova criatura. A posição física das recompensas e sua história no encontro permanecem a definir. A Chave do Guardião segue fora deste sorteio.

## Utilidade atual e futura

**Uso atual no jogo:** nenhum novo uso implementado nesta tarefa; ficha e imagem existem apenas no GDD.

**Função proposta:** Dinâmica futura: posicionar no chão, iluminar, recolher e reposicionar. Após três posicionamentos, ao recolher pela terceira vez, passa ao estado danificado sem desaparecer. O equipamento danificado permanece persistente e pode futuramente ser restaurado na Oficina de Cedric ou vendido como sucata à Guilda.

**Dependências ainda abertas:** Raio, combustível, duração, contagem entre sessões e efeito da condição danificada sobre a iluminação a definir. Não presumir ligação funcional com ITEM-032.

## Comercialização e relação com NPCs

Venda da versão danificada como sucata é uma proposta futura. Valor e possibilidade de vender a versão normal não definidos; nenhuma compra disponível no jogo.

Mestre Cedric: restauração futura. Atendente de Espólios e Contratos e Tesouraria: avaliação e pagamento futuros de sucata. Sem serviços ou receitas implementados.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-036.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D, cadastro no BancoDeItens e implementação:** pendentes.
- **Testes de gameplay e validação final:** não realizados; a tarefa é exclusivamente documental e visual.

## Estados e ciclo propostos

| Estado / momento | Comportamento pretendido |
|---|---|
| Normal | Item portátil persistente, passível de posicionamento futuro. |
| Posicionado | Ilumina o local; raio, combustível e duração ainda não definidos. |
| Primeiro e segundo recolhimentos | Volta ao inventário para reposicionamento. |
| Terceiro posicionamento | Continua o ciclo até ser recolhido. |
| Recolhimento após o terceiro posicionamento | Passa a **danificado**, sem desaparecer. |
| Danificado | Permanece como estado do mesmo equipamento; uso luminoso nessa condição a definir. Restauração por Cedric e venda de sucata são propostas futuras. |

Não criar outro ITEM para a condição danificada, não zerar automaticamente o contador e não implementar reparo ou desgaste global agora. O modo de persistir o contador e o estado será decidido na implementação autorizada.

## Referência do catálogo

[Espólios do Guardião](CATALOGO-ESPOLIOS-GUARDIAO-PISO1.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
