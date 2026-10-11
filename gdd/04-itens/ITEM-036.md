---
id: "ITEM-036"
nome: "Candelabro de Expedição"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Equipamento utilitário / iluminação portátil"
raridade: "Raro"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
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

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-036; **coleção:** Guardião Ancestral.
- **Categoria:** Equipamento utilitário / iluminação portátil.
- **Raridade proposta:** Raro; não determina uma probabilidade de drop.
- **Nome no catálogo:** Candelabro de Expedição.
- **ID de runtime:** `candelabro_expedicao`; GDD `ITEM-036`.
- **Aparência:** Candelabro compacto com base estável e suporte metálico para transporte. O desenho de fontes de luz na miniatura é conceitual; não estabelece combustível, duração ou alcance.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Candelabro portátil de metal, pensado para iluminar câmaras e passagens.

**Descrição detalhada:** Candelabro compacto com base estável e suporte metálico para transporte. O desenho de fontes de luz na miniatura é conceitual; não estabelece combustível, duração ou alcance. Utilitário proposto para expedições prolongadas. Criador e antiga expedição não definidos. Sem origem mágica ou ancestral especial confirmada.

## História, origem e limites narrativos

Utilitário proposto para expedições prolongadas. Criador e antiga expedição não definidos. Sem origem mágica ou ancestral especial confirmada.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual após a derrota do **Guardião Ancestral do Piso 1 — BEST-002**. A chave é independente e não participa do sorteio. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Coletável individual raro do Guardião, persistente no alforge e consultável. Posicionamento, luz, três recolhimentos, estado danificado, reparo e sucata permanecem futuros.

**Direção de design aprovada (uso disponível conforme acima):** Dinâmica futura: posicionar no chão, iluminar, recolher e reposicionar. Após três posicionamentos, ao recolher pela terceira vez, passa ao estado danificado sem desaparecer. O equipamento danificado permanece persistente e pode futuramente ser restaurado na Oficina de Cedric ou vendido como sucata à Guilda.

**Dependências ainda abertas:** Raio, combustível, duração, contagem entre sessões e efeito da condição danificada sobre a iluminação a definir. Não presumir ligação funcional com ITEM-032.

## Comercialização e relação com NPCs

Venda da versão danificada como sucata é uma proposta futura. Valor e possibilidade de vender a versão normal não definidos; nenhuma compra disponível no jogo.

Mestre Cedric: restauração futura. Atendente de Espólios e Contratos e Tesouraria: avaliação e pagamento futuros de sucata. Sem serviços ou receitas implementados.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-036.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

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
