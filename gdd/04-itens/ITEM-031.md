---
id: "ITEM-031"
nome: "Fragmento de Registro Antigo"
funcao: "Recompensa do Piso 1 — integração inicial"
tipo: "Documento narrativo / objeto comercial"
raridade: "Raro"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1"
relacionados:
  - "GAME-013"
  - "DNG-014"
  - "DNG-013"
  - "GAME-009"
  - "GAME-010"
  - "ITEM-004"
  - "ITEM-005"
  - "ITEM-038"
  - "DOS-001"
  - "DOS-005"
  - "GAME-005"
imagem: "./assets/itens/ITEM-031.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-11"
---

# Fragmento de Registro Antigo

> **PARTE 2 — IMPLEMENTAÇÃO INICIAL EM 11/10/2026.** Cadastro, inspeção e persistência foram integrados ao Studio. Uso atual está descrito abaixo; funções futuras e narrativa proposta não são funcionalidades disponíveis. TESTADO em cenários definidos em GAME-013; aprovação final e multiplayer real pendentes.

## Identificação e aparência

- **ID:** ITEM-031; **coleção:** Baú Verdadeiro.
- **Categoria:** Documento narrativo / objeto comercial.
- **Raridade proposta:** Raro; não determina uma probabilidade de drop.
- **Nome no catálogo:** Fragmento de Registro Antigo.
- **ID de runtime:** `fragmento_registro_antigo`; GDD `ITEM-031`.
- **Aparência:** Fragmento de pergaminho envelhecido, bordas irregulares e marcas de escrita. A miniatura não deve inventar mapa, brasão ou coordenadas. O texto legível completo está na documentação.
- **Propriedades confirmadas:** somente as características materiais e a direção de uso descritas nesta solicitação. Não há efeito mágico ou bônus adicional aprovado para este item.

## Descrições consultáveis

**Descrição curta para o inventário:** Registro incompleto de um guerreiro antigo, com uma pista sobre um elmo singular em Arkham.

**Descrição detalhada:** Fragmento de pergaminho envelhecido, bordas irregulares e marcas de escrita. A miniatura não deve inventar mapa, brasão ou coordenadas. O texto legível completo está na documentação. Documento proposto como início de uma investigação futura sobre o Elmo de Vidro. Seu relato é uma pista narrativa sujeita à validação canônica, não prova da identidade de um guerreiro ou de um ferreiro.

## História, origem e limites narrativos

Documento proposto como início de uma investigação futura sobre o Elmo de Vidro. Seu relato é uma pista narrativa sujeita à validação canônica, não prova da identidade de um guerreiro ou de um ferreiro.

Os fatos canônicos usados como referência não transformam hipóteses deste item em fatos históricos. Não foram inventados proprietários, fabricantes, datas, brasões ou poderes para preencher lacunas.

## Obtenção atual

Sorteio individual do **Baú Verdadeiro do Piso 1**. Valores, pesos, quantidades, elegibilidade, redução diária e testes em [GAME-013](../02-gameplay/GAME-013.md). Não integra os espólios do Baú Falso.

## Utilidade atual e futura

**Uso atual no jogo:** Coletável individual raro do Baú Verdadeiro. LER REGISTRO exibe o texto fixo e registra DIARIO-CAP1-005 permanentemente; não consome o papel, não inicia missão e não exige manter o objeto para preservar o conhecimento.

**Direção de design aprovada (uso disponível conforme acima):** Leitura desbloqueia conhecimento permanente no Diário de John. O papel físico poderá continuar no alforge e ser vendido depois; vender ou perder o papel não deverá apagar o conhecimento já registrado. Leitura e memória permanente implementadas; venda permanece futura.

**Dependências ainda abertas:** Leitura requer o objeto e registra DIARIO-CAP1-005. Histórico e cadeia de investigação permanecem para definição futura.

## Comercialização e relação com NPCs

Documento legível e comercializável por proposta. Preço e processo de avaliação a definir; não vender automaticamente ao ler.

John registra a descoberta; Mestre Cedric poderá ser consultado futuramente para investigar registros herdados de seu avô. Diálogo, missão e recompensa não implementados.

Preços, receitas, contratos e serviços não são disponibilizados por esta documentação. A economia existente permanece intacta.

## Miniatura e implementação

- **Caminho da arte:** `./assets/itens/ITEM-031.png`.
- **Identidade visual:** referência direta da imagem publicada da Oficina de Mestre Cedric e do Peitoral de Vidro; nome na própria arte, tipografia creme/dourada, faixa preta e moldura ornamentada. Dimensão final 1672 × 941.
- **Miniatura:** PRODUZIDA E CONFERIDA visualmente nesta etapa; arquivo real em 1672 × 941, com nome dentro da arte. Aprovação artística final pelo usuário ainda pendente.
- **Modelo 3D:** não criado nesta etapa. **BancoDeItens, informações, inspeção/alforge e persistência:** cadastrados. Miniatura de gameplay gerada pela interface nativa; a arte PNG do GDD não foi importada como asset Roblox.
- **Testes:** sorteios, transações e miniaturas conferidos; usos específicos e limites em GAME-013. Não marcar como VALIDADO; multiplayer real e avaliação final pendentes.

## Texto legível e conhecimento permanente

O texto integral **Registro de um Guerreiro Esquecido** está em [DOS-005](../06-dossie/DOS-005.md). É proposta narrativa sujeita à validação canônica. A descoberta fica separada da posse do papel: ler → registrar conhecimento persistente; eventual venda futura não apagará a entrada. Reler não duplica a descoberta. Diálogo com Cedric e investigação permanecem futuros.

## Referência do catálogo

[Recompensas do Baú Verdadeiro](CATALOGO-RECOMPENSAS-BAU-VERDADEIRO.md) · [Consolidação do Piso 1](../07-masmorras/DNG-014.md).
