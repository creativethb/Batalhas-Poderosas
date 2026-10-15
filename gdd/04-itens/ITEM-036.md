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
data_atualizacao: "2026-10-15"
---

# Candelabro de Expedição

> **Estado revisto em 15/10/2026:** recompensa e uso funcional integrados ao sistema existente. Abaixo estão separados implementação, valores provisórios e funções futuras. Testes locais não equivalem a validação final ou multiplayer real.

## Identificação e aparência

- **ID:** ITEM-036; **coleção:** Guardião Ancestral.
- **Categoria:** Equipamento utilitário / iluminação portátil.
- **Raridade proposta:** Raro; não determina uma probabilidade de drop.
- **Nome no catálogo:** Candelabro de Expedição.
- **ID de runtime:** `candelabro_expedicao`; GDD `ITEM-036`.
- **Aparência:** Candelabro compacto com base estável e suporte metálico para transporte. A arte inicial é conceitual; o modelo integrado usa recipientes protegidos de líquido luminoso. Parâmetros provisórios de iluminação estão na seção de uso, sem combustível externo implementado.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Candelabro portátil de metal, pensado para iluminar câmaras e passagens.

**Descrição detalhada:** Candelabro compacto com base estável e suporte metálico para transporte. A arte inicial é conceitual; o modelo integrado usa recipientes protegidos de líquido luminoso. Parâmetros provisórios de iluminação estão na seção de uso, sem combustível externo implementado. Utilitário proposto para expedições prolongadas. Criador e antiga expedição não definidos. Sem origem mágica ou ancestral especial confirmada.

## História, origem e limites narrativos

Utilitário proposto para expedições prolongadas. Criador e antiga expedição não definidos. Sem origem mágica ou ancestral especial confirmada.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual após a derrota do **Guardião Ancestral do Piso 1 — BEST-002**. A chave é independente e não participa do sorteio. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual:** ação **LANCAR** diretamente no alforge, sem equipagem manual. O menu fecha antes do gesto; a espada é guardada temporariamente durante o arremesso e retorna ao estado de saque anterior. Trajetória em arco respeita obstáculos e coloca o objeto iluminando o chão.

Ao aproximar, o proprietário vê um aviso compacto **E COLETAR** (122×32 pixels lógicos), sem abrir a janela de espólios. Um objeto ativo por jogador; validações e estoque permanecem no servidor/sistema existente.

`ConfiguracaoCandelabro` centraliza os valores provisórios: três usos, distância de lançamento 12 studs e luz de alcance 48/intensidade 3. Cada unidade mantém estado em `perfil.Candelabros.Unidades`. O terceiro recolhimento torna a unidade danificada; um quarto lançamento é bloqueado. O item permanece no inventário e a recuperação de sessão conserva desgaste.

**Ainda futuro:** manutenção em Cedric, venda como sucata, preços, abastecimento e consumo de ITEM-032. Não presumir combustível externo funcional ou serviço disponível.

**Visual:** modelo único com recipientes protegidos de líquido luminoso, conforme direção aprovada. Não estabelece composição/receita do líquido. Dano é indicado por Highlight; os vidros não se quebram individualmente nessa malha.

**Testes:** Play com três lançamentos/coletas, luz, posse, bloqueio de duplicação/quarto uso, preservação da unidade e desgaste; revisão direta testou clique LANCAR, fechamento do menu, retorno da espada e coleta E. Não testados multiplayer, telefone/controle físicos ou manutenção.

## Comercialização e relação com NPCs

Venda da versão danificada como sucata é uma proposta futura. Valor e possibilidade de vender a versão normal não definidos; nenhuma compra disponível no jogo.

Mestre Cedric: restauração futura. Atendente de Espólios e Contratos e Tesouraria: avaliação e pagamento futuros de sucata. Sem serviços ou receitas implementados.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-036.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** integrado ao Studio em etapa posterior à arte inicial; encaixe/uso descritos nesta ficha. **BancoDeItens, informações, inspeção/alforge e persistência:** existentes preservados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Estados e ciclo implementados

| Momento | Comportamento atual |
|---|---|
| Normal no alforge | Persistente; ação LANCAR disponível quando elegível. |
| Lançado | Ilumina no chão; coleta exclusiva do proprietário. |
| Primeiro e segundo recolhimentos | Retorna ao inventário conservando usos. |
| Terceiro recolhimento | Torna-se danificado, sem desaparecer. |
| Danificado | Permanece no inventário; novo lançamento bloqueado. Reparo/sucata futuros. |

Não criar outro ITEM para a condição danificada nem zerar automaticamente seu contador. Modelo físico e estado de desgaste não acrescentam um sistema global de durabilidade.

## Referência do catálogo

[Espólios do Guardião](CATALOGO-ESPOLIOS-GUARDIAO-PISO1.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
