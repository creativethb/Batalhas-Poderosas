# MANUAL OPERACIONAL DOS AGENTES — GDD BATALHAS PODEROSAS
Este documento estabelece o protocolo obrigatório de leitura, escrita, padronização e sincronização para qualquer Agente de IA (Bibliotecário, Designer de Lore, Engenheiro de Gameplay) que atue no repositório `creativethb/Batalhas-Poderosas`.

---

## 1. Regra de Ouro: Sincronização Dupla Obrigatória

O repositório possui duas camadas que **sempre** devem refletir a mesma verdade:
1. **Camada Documental:** Arquivos `.md` dentro de `/gdd/`.
2. **Camada Visual:** O mini-site `index.html` na raiz, servido pelo GitHub Pages.

> **Comando de Execução:** Toda vez que você criar ou atualizar uma entidade em `/gdd/`, você DEVE atualizar o objeto `defaultData` dentro de `index.html` para que o mini-site exiba a alteração em produção imediatamente após o commit.

---

## 2. Nomenclatura e IDs Estáveis

Nunca invente prefixos novos. Use rigorosamente os identificadores abaixo em maiúsculas com preenchimento de três dígitos:

| Categoria | Prefixo | Exemplo de Arquivo em `/gdd/` | Destino de Imagens em `/assets/` |
| :--- | :--- | :--- | :--- |
| **NPCs** | `NPC-XXX` | `gdd/03-npcs/NPC-001-mestre-cedric.md` | `assets/npcs/NPC-001.png` |
| **Itens / Armas** | `ITEM-XXX` | `gdd/04-itens/ITEM-001-madeira-comum.md` | `assets/itens/ITEM-001.png` |
| **Locais / Cenas** | `LOCAL-XXX` | `gdd/05-locais/LOCAL-001-casa-de-john.md` | `assets/locais/LOCAL-001.png` |
| **Cânone / Regras** | `CANON-XXX` ou `BP-2026-XXX` | `gdd/99-canon/CANON-001-protagonista-john.md` | — |
| **Gameplay / Lógica** | `GAME-XXX` | `gdd/02-gameplay/GAME-001-loop-principal.md` | — |
| **História / Lore** | `LORE-XXX` | `gdd/01-lore/LORE-001-origem-de-arkan.md` | — |

---

## 3. Padrão Estrito de Cabeçalho (Frontmatter YAML)

Nenhum arquivo dentro de `/gdd/` pode existir sem o bloco YAML inicial delimitado por `---`. Preencha todos os campos obrigatórios:

```yaml
---
id: "NPC-001"
nome: "Mestre Cedric"
funcao: "Ferreiro da Vila"
status: "CANONICO"
localizacao: "Oficina de Arkham"
relacionados:
  - "LOCAL-002"
  - "ITEM-001"
  - "GAME-002"
imagem: "./assets/npcs/NPC-001.png"
atualizado_por: "agente_bibliotecario"
data_atualizacao: "2026-09-08"
---

# Biografia & Propósito
Conteúdo descritivo aqui em Markdown puro...
```

Valores permitidos para `status`:
- `CANONICO`: Oficializado e imutável sem ordem humana.
- `EM_DESENVOLVIMENTO`: Sendo implementado nos scripts Luau ou modelagem.
- `IDEIA`: Proposta em discussão.
- `PLANEJADO`: Aprovado para fases futuras.
- `DESCONTINUADO`: Ideia abandonada ou substituída.

---

## 4. Protocolo de Proteção ao Cânone

- **Prioridade Máxima:** Antes de redigir qualquer lore, diálogo ou mecânica, leia os arquivos da pasta `/gdd/99-canon/`.
- **Imutabilidade:** Itens marcados como `CANONICO` NÃO podem ser removidos, renomeados ou ter sua essência alterada por decisão autônoma de agente.
- **Substituição Formal:** Se uma nova decisão substituir uma anterior, a nova decisão deve apontar o ID da antiga no campo `substitui: "CANON-XXX"`, e a antiga deve ter seu status alterado para `DESCONTINUADO`.

---

## 5. Diretrizes para Mídia e Imagens

- Salve as imagens exclusivamente nas subpastas de `/assets/`.
- O nome da imagem deve conter o ID da entidade (ex: `assets/npcs/NPC-002.png`).
- Ao referenciar imagens no Markdown ou no HTML, sempre utilize caminhos relativos iniciando com `./assets/...`. Nunca use caminhos absolutos de disco local (ex: `F:\...`).

---

## 6. Rotina Passo a Passo para Novas Demandas

Sempre que o usuário solicitar uma alteração ou adição:

1. **Checagem de Consistência:** Verifique se o ID a ser usado já existe no diretório. Use sempre o próximo número disponível (`NPC-008`, `LOCAL-009`, etc.).
2. **Criação do Documento:** Crie o `.md` na pasta correspondente de `/gdd/` com Frontmatter completo.
3. **Criação do Asset:** Se houver imagem gerada, salve na pasta correspondente em `/assets/`.
4. **Atualização do index.html:** Localize o array correspondente (`npcs`, `itens`, `locais`, etc.) dentro de `defaultData` no `index.html` e insira o novo objeto espelhando os dados do Markdown.
5. **Commit Semântico:** Faça o commit seguindo o padrão:
   - `docs(npc): adicionar NPC-008 NomeDoNPC`
   - `feat(gameplay): balancear dano da espada ITEM-003`
   - `canon(core): registrar CANON-006 RegraX`
6. **Push:** Envie as mudanças para a branch `main`.

---

## 7. Protocolo de Segurança de Credenciais (Crítico)

- **NUNCA** faça commit, log ou espelhamento do Personal Access Token (PAT) do GitHub em nenhum arquivo versionado (`.md`, `.json`, `.txt`, `.html`, scripts ou relatórios).
- O token deve existir unicamente em variáveis voláteis de ambiente durante a sessão do terminal.
