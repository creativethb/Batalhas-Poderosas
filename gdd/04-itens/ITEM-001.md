---
id: "ITEM-001"
nome: "Madeira Comum"
status: "CANONICO"
relacionados:
  - "NPC-001"
  - "NPC-014"
  - "ITEM-002"
  - "ITEM-003"
  - "GAME-001"
imagem: "./assets/itens/ITEM-001.png"
atualizado_por: "Codex"
data_atualizacao: "2026-10-15"
---

# Ficha de Item: Madeira Comum

## 1. Dados Básicos
- **ID de runtime:** `madeira_comum` (identificador documental legado: `Madeira`).
- **Tipo:** Material de Criação / Recurso Base
- **Raridade:** Comum (Branco)
- **Local de Obtenção:** aos pés da Árvore Ancestral, situada atrás da igreja de Arkham.

> A origem narrativa definida em 12/10/2026 é um pedaço de madeira de forma quadrada aos pés da Árvore Ancestral. A Casa de John e o estabelecimento comercial são rotas antigas. A coleta individual está implementada no ponto atrás da igreja; ver GAME-001.

## 2. Descrição
Madeira comum utilizada como recurso de criação, recolhida inicialmente aos pés da misteriosa Árvore Ancestral de folhas quadradas. No primeiro ciclo de preparação de John, ele obtém um pedaço desse material e o leva ao padre da vila para receber a unção.

## 3. Transformação por atributo

A Madeira Comum **não deixa de existir como item-base no catálogo** e não deve ser renomeada na origem.

Durante a gameplay:
1. John coleta/obtém a **Madeira Comum**.
2. Leva o mesmo material ao padre.
3. O padre realiza o rito de unção.
4. A própria madeira recebe o estado/atributo **Ungida**.
5. A partir desse momento, aquela instância passa a ser reconhecida e apresentada ao jogador como **Madeira Ungida**.

Portanto, a Madeira Ungida não é um segundo recurso coletado no mundo: é a Madeira Comum transformada pelo rito.

**IMPLEMENTADO / TESTADO localmente:** o estado de unção é mantido no progresso persistente existente, sem criar outro ID de item. BancoDeItens/BP_ItemInterface apresentam origem, descrição e nome contextual de Madeira Ungida. Repetições não duplicam o material; o servidor revalida o rito antes do commit. Reconexão física e multiplayer real permanecem pendentes.

## 4. Distinção da Madeira Sagrada

**Madeira Ungida** e **Madeira Sagrada** não são o mesmo material.

- Madeira Ungida: Madeira Comum transformada pela unção do padre.
- Madeira Sagrada: galho/material proveniente da Árvore Sagrada e ligado a Eldrin.

Cedric deverá receber os dois materiais no ciclo inicial de fabricação da espada.

## 5. Uso no ciclo inicial

A primeira forja existente reconhece o estado de unção e consome uma unidade de cada material. O nome atual da espada é preservado (ITEM-003):

**Madeira Comum → unção pelo padre → Madeira Ungida**

somada à:

**Madeira Sagrada → proveniente da Árvore Sagrada**

→ materiais entregues a **Mestre Cedric** para a fabricação da espada de treinamento de John.
