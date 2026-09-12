# PROMPT DE MISSÃO — UPGRADE DO MINI-SITE DO GDD (BATALHAS PODEROSAS)

> **Destinado ao agente que fará o upgrade do mini-site.**
> Copie este documento inteiro (ou aponte o repositório `F:\Bibliotecário_GDD`) e execute os requisitos abaixo.

---

## 1. SEU PAPEL

Você é o **Engenheiro do Mini-site do GDD Vivo de Batalhas Poderosas** (Reino de Arkan). Seu trabalho é transformar o `index.html` atual (single-file) em uma plataforma de documentação completa, com:

1. **Banco de dados consultável diretamente no mini-site** (todas as categorias e entidades navegáveis, com busca, filtros e detalhamento).
2. **Edição e criação FULL — capazes de criar ENTIDADES, CATEGORIAS INTEIRAS e EDITAR qualquer registro**, persistindo via GitHub API (Contents API) na branch `main` do repositório `creativethb/Batalhas-Poderosas`.
3. **Sincronização dupla com a camada documental** (`/gdd/*.md`) conforme o protocolo abaixo.

IMPORTANTE: o mini-site publicado no GitHub Pages é a **camada de apresentação ao público** e o **painel de trabalho dos autores/agentes**. Ele deve espelhar fielmente os arquivos Markdown em `/gdd/`.

---

## 2. ÁRVORE COMPLETA DO REPOSITÓRIO

```
F:\Bibliotecário_GDD\
│
├── .gitignore
├── AGENTS.md                     ← PROTOCOLO OBRIGATÓRIO DOS AGENTES (LEIA ANTES DE EDITAR)
├── index.html                    ← MINI-SITE ATUAL (GDD Vivo, GitHub Pages) — ALVO DO UPGRADE
├── INDICE.md                     ← Índice geral de entidades do GDD
├── MEMORIA_BIBLIOTECARIO.md      ← Memória persistente do agente Bibliotecário (registro de sessões)
├── opencode.json
├── README.md                     ← Obs: desatualizado (fala de Unity/PixelArt 2D). O projeto real é Roblox Studio (Luau + Rojo) — ver AGENTS.md e index.html
│
├── assets\
│   ├── itens\    ITEM-001.png … ITEM-004.png
│   ├── locais\   LOCAL-001.png … LOCAL-008.png   (falta LOCAL-009)
│   └── npcs\     NPC-000.png … NPC-012.png       (novas: NPC-013.jpg… podem ser criadas)
│
├── banco_narrativo\              ← NARRATIVA PROFUNDA (INTERNO). NÃO EXPOR NO MINI-SITE PÚBLICO.
│   ├── README.md
│   ├── 01-personagens\    _TEMPLATE_PERSONAGEM.md, PERS-001-REI-MAGO.md, PERS-002-CEDRIC.md
│   ├── 02-cronologia\     CRONOLOGIA_MESTRE.md
│   ├── 03-segredos-e-revelacoes\  MATRIZ_SEGREDOS.md
│   ├── 04-mapa-relacoes\  MAPA_RELACOES.md
│   └── 05-regras-de-mundo\  REGRAS_METAFISICAS.md
│
└── gdd\                          ← CAMADA DOCUMENTAL (FONTE DE VERDADE DO MINI-SITE)
    ├── 01-lore\      LORE-001 … LORE-006
    ├── 02-gameplay\  GAME-001 … GAME-006
    ├── 03-npcs\      NPC-000 … NPC-013
    ├── 04-itens\     ITEM-001 … ITEM-004
    ├── 05-locais\    LOCAL-001 … LOCAL-009
    └── 99-canon\     CANON-001 (BP-2026-001) … CANON-008 (BP-2026-008)
```

---

## 3. O MINI-SITE ATUAL (O QUE JÁ EXISTE)

O `index.html` é **single-file** (~3500 linhas) com:

- **Tema medieval** personalizado: paleta `arkan` (escuro + dourado `#d4af37` + pergaminho), fontes Cinzel/Inter/JetBrains Mono, componente `medieval-card`, painel canônico. **Preserve a identidade visual.**
- **`const defaultData = { ... }`** — o "banco" inicial hardcoded no JS com estas coleções:

| Coleção | Array | Campos-chave |
| :--- | :--- | :--- |
| `projeto` | objeto | nome, universo, versao, ultimaAtualizacao, estado, engine, autor |
| `npcs` | array | id, nome, funcao, localizacao, status, imagem, relacionados[], dialogos[], markdown |
| `itens` | array | id, nome, tipo, raridade, status, imagem, relacionados[], markdown |
| `locais` | array | id, nome, tipo, status, imagem, relacionados[], markdown |
| `decisoes` | array | id, titulo, data, categoria, status, motivo, substitui, relacionados[], markdown |
| `sistemas` | array | id, nome, categoria, status, markdown |
| `livro` | array | id, capitulo, titulo, subtitulo, status, cronicas[{id,titulo,status,fonte,texto}] |
| `diario` | array | id, capitulo, capituloTitulo, titulo, momento, local, eventoGatilho, condicao, obrigatorio, estado, missao, status, continuidade, texto |
| `missoes` | array | id, nome, status, dadorId, recompensa, relacionados[], markdown |
| `changelog` | array | data, versao, tipo, mudancas[] |

- **Rotas hash**: `#dashboard, #historia, #livro, #diario, #locais, #npcs, #gameplay, #sistemas, #itens, #missoes, #canon, #referencias, #changelog, #estado, #timeline, #saude`.
- **Modo Editor atual**: drawer lateral que edita **um registro por vez** via `commitToGitHub()` (GitHub Contents API, branch `main`) + `localStorage('bp_gdd_db')` como cache; validação de token com repositório/branch/PAT no modal de auth.
- **Páginas dinâmicas**: `renderDashboard`, `renderNPCs`, `renderLocais`, `renderItens`, `renderCanon`, `renderSistemas`, `renderMissoes`, `renderLivro` (tomo medieval ilustrado), `renderDiario` (tabs Leitura/GDD), `renderHistoria`, `renderReferencias`, `renderChangelog`, `renderEstado`, `renderTimeline`, `renderSaude` (auditoria de consistência).

---

## 4. O QUE PRECISA SER CRIADO/MELHORADO (REQUISITOS)

### 4.1. Banco de dados 100% consultável no mini-site
- **Todas as coleções** (npcs, itens, locais, decisoes, sistemas, livro, diario, missoes, lore) navegáveis por páginas dedicadas.
- **Busca global** já existente deve passar a indexar **todas** as entidades e campos (incluindo `markdown`, `continuidade`, `texto`).
- **Filtros** por: categoria, status de canonização (`CANONICO`, `EM_DESENVOLVIMENTO`, `IDEIA`, `PLANEJADO`, `DESCONTINUADO`), relacionamentos.
- **Detalhamento individual**: ao selecionar uma entidade (ex: `#npcs/NPC-005`), mostrar ficha completa + relacionados clicáveis + localização + imagem.
- **Página de busca/índice agregado**: painel que cruza referências entre coleções (quem cita quem) — aproveite/exonere a lógica de `renderSaude`.

### 4.2. CRUD de categorias INTEIRAS
- **Criar nova categoria de conteúdo** no mini-site deve gerar: novo array em `defaultData`, nova rota/hash, nova página de listagem, formulário de criação com os campos adequados, e o arquivo `.md` correspondente em `/gdd/` (com frontmatter YAML válido).
- **Editar metadados de categoria** (nome da categoria, descrição, ícone, local em `/gdd/`).
- **Letrados**: adicionar/remover/renomear campos das entidades de uma categoria a partir da interface.
- Toda criação/edição deve persistir via GitHub API (Contents API → commit na branch `main`) e atualizar o `defaultData` + `localStorage`.

### 4.3. Editor de entidades robusto
- Formulário dinâmico conforme a coleção (campos diferentes por categoria).
- Pré-visualização Markdown ao vivo (já existe, manter).
- Gerenciamento de **imagens**: upload/URL, com fallback se ausente.
- Gerenciamento de **relacionamentos**: multiselect com sugestão de IDs existentes.
- **Validação** antes do commit: ID estável obrigatório, status válido, frontmatter bem formado.

### 4.4. Sincronização documental (REVERSE & FORWARD)
- **Leitura**: ao abrir o site, o `defaultData` pode ser construído a partir dos arquivos `/gdd/`. Mantenha a equivalência com o git.
- **Escrita**: cada entidade salva reflete em `gdd/<pasta>/<ID>.md` com frontmatter completo:
  ```yaml
  ---
  id: "NPC-XXX"
  nome: "..."
  status: "CANONICO"
  atualizado_por: "agente_bibliotecario"
  data_atualizacao: "YYYY-MM-DD"
  ---
  ```
- Nunca quebrar a sincronização entre camada documental, `defaultData` e mini-site.

### 4.5. Cache do navegador (problema conhecido)
- Imagens/instância não atualizam sem navegação anônima. Corrigir com cache-busting: query string versionada (`?v=`) ou meta tags `no-cache`. Ancorar ao `projeto.versao`.

### 4.6. Segurança de credenciais
- **NUNCA** commitar PAT em arquivo versionado. O token fica em `localStorage` do navegador (já existente) ou via variável de ambiente do agente. Não criar nenhum arquivo com secrets.

---

## 5. PADRÕES E REGRAS DO PROJETO (AGENTS.md — RESUMO)

1. **Sincronização dupla obrigatória**: camada documental (`/gdd/`) ⇄ camada visual (`index.html` → `defaultData`).
2. **Nomenclatura estável** (prefixos maiúsculos de 3 dígitos):
   - `NPC-XXX` → `gdd/03-npcs/`, imagem `assets/npcs/NPC-XXX.png|jpg`
   - `ITEM-XXX` → `gdd/04-itens/`
   - `LOCAL-XXX` → `gdd/05-locais/`
   - `CANON-XXX` / `BP-2026-XXX` → `gdd/99-canon/`
   - `GAME-XXX` → `gdd/02-gameplay/`
   - `LORE-XXX` → `gdd/01-lore/`
   - `PERS-XXX` → `banco_narrativo/01-personagens/` (INTERNO)
3. **Frontmatter YAML obrigatório** em todo `.md` (não existe `.md` sem o bloco `---`).
4. **Status permitidos**: `CANONICO` / `EM_DESENVOLVIMENTO` / `IDEIA` / `PLANEJADO` / `DESCONTINUADO`.
5. **Cânone imutável**: entidades `CANONICO` não podem ser removidas/renomeadas sem ordem humana. Substituições usam campo `substitui:` e a antiga vai para `DESCONTINUADO`.
6. **Imagens**: sempre caminho relativo `./assets/...`. Nunca caminho absoluto de disco.
7. **Commit semântico**: `docs(npc): ...`, `feat(gameplay): ...`, `canon(core): ...`.
8. **banco_narrativo é INTERNO**: segredos, misterios, matriz epistemológica e identidade do Rei Mago não vão para a camada pública. O mini-site consome `/gdd/`.

---

## 6. VALIDAÇÃO DA ENTREGA

1. O mini-site continua single-file ou multi-file? **Permitido multi-file**, mas o GitHub Pages deve servir normalmente (sem build server; só estático). Se mantiver single-file, organize o JS.
2. Testar localmente abrindo `index.html` — tudo deve funcionar sem console errors.
3. Testar o fluxo CRUD com token de teste (o enginheiro terá acesso ao repo `creativethb/Batalhas-Poderosas` na branch `main`).
4. Verificar sincronização: criar/editar entidade → conferir commit criado no GitHub → recarregar site → ver mudança refletida.
5. Verificar busca indexando todas as coleções.
6. Preservar as páginas existentes (livro/tomo, diário, dashboard, auditoria) e melhorar sem quebrar.
7. Não commitar a nova versão com o `defaultData` vazio ou quebrado. Fazer commits semânticos parcelados.

---

## 7. ENTREGA FINAL

- Código atualizado no repositório (branch `main`).
- `MEMORIA_BIBLIOTECARIO.md` atualizado com a nova capacidade do mini-site.
- `INDICE.md` atualizado se novas categorias forem criadas.
- Relatório curto ao usuário: o que foi implementado, o que mudou no arquivo, como acessar, e pendências.