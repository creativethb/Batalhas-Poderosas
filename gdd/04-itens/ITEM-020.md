---
id: "ITEM-020"
nome: "Placa de Carapaça"
funcao: "Material coletável de Cascudo"
tipo: "Material"
raridade: "Comum"
status: "EM_DESENVOLVIMENTO"
localizacao: "Masmorra — Piso 1 "
relacionados:
  - "BEST-021"
  - "GAME-009"
  - "GAME-011"
imagem: "./assets/itens/ITEM-020.svg"
atualizado_por: "Codex"
data_atualizacao: "2026-10-09"
---

# Placa de Carapaça

> **IMPLEMENTADO / TESTADO EM PLAY LOCAL — identidade, arte e economia provisórias.** Autorização de 09/10/2026. Não equivale a VALIDADO pelo responsável.

## Identificação e informações consultáveis

- **ID documental:** ITEM-020. **ID de runtime:** `placa_carapaca`.
- **Categoria:** Material. **Raridade:** Comum. **Origem:** Cascudo (BEST-021), corpos derrotados no Piso 1.
- **Descrição curta:** Fragmento da proteção externa do Cascudo.
- **Descrição completa:** Placa recuperada após derrotar o Cascudo; aparência e composição ainda sujeitas a refinamento.
- **Propriedades:** Origem na proteção externa; composição química não confirmada.

## Obtenção provisória

Interação **Examinar** no corpo derrotado. Sorteio único e compartilhado, com 20% de vazio forçado. Nos demais resultados, chance independente de **55%**, quantidade **1–2**. As falhas de todas as entradas também podem produzir saque vazio. Moedas da criatura constam em GAME-011.

Coleta seletiva com revisões no servidor; fechar/reabrir não altera o resultado. O corpo permanece disponível enquanto a sala está ocupada, respeitando a limpeza existente de GAME-011.

## Uso atual

Coletar, guardar no alforge e consultar informações. Material empilhável e persistente pelo InventarioService/BP_DataStore_V1 existentes. Sem consumo, fabricação, venda ou efeito de equipamento nesta etapa.

## Possibilidades futuras

Artesanato e reforços. Possibilidades futuras, sem receita, preço, comprador, contrato, bônus ou aprimoramento disponível.

## Representação e integração

Miniatura estilizada nativa em BP_ItemInterface, sem imagens externas. Representação vetorial de referência: `./assets/itens/ITEM-020.svg`. Arte provisória, sem estabelecer anatomia ou poderes.

BancoDeItens fornece nome, descrições, categoria, raridade, origem, propriedades e usos para inspeção, alforge e ficha independente. EspoliosConfig/EspoliosService reutilizados; carteira e persistência preservadas.

## Testes e pendências

Play local: rotina real de derrota e registro, saque vazio, coleta parcial e restante, reabertura, rejeição de replay/quantidades inválidas, coleta do material e moedas. Miniatura e ficha criadas no cliente. Export/Import dos 12 materiais exercitado.

**Pendentes:** multiplayer real com vários clientes, salvar/recarregar entre servidores reais, validação artística, identidade final e economia. Nenhuma receita, venda ou contrato implementado.

Ver [catálogo consolidado](CATALOGO-ESPOLIOS-PROPOSTOS.md) e [sistema](../02-gameplay/GAME-011.md).
