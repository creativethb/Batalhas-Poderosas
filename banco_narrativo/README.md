# 🗄️ BANCO DE CONHECIMENTO NARRATIVO — BATALHAS PODEROSAS
> **DIRETÓRIO INTERNO DO BIBLIOTECÁRIO & AUTORES**  
> **NÃO PUBLICAR COMO PÁGINA PÚBLICA DO GDD.**  
> **FUNÇÃO:** Base de consulta, rastreamento de continuidade, cronologia profunda, segredos de roteiro e prevenção de contradições.

---

## 1. Princípio Fundamental de Arquitetura

```
┌─────────────────────────────────────────────────────────┐
│        🗄️ BANCO DE CONHECIMENTO NARRATIVO (INTERNO)     │
│   (História profunda, cronologia, segredos, matrizes)   │
└───────────────────────────┬─────────────────────────────┘
                            │  Promoção / Decisão Canônica
                            ▼
┌─────────────────────────────────────────────────────────┐
│               🌐 GDD VIVO (DOCUMENTAÇÃO OFICIAL)        │
│   (Fichas técnicas, itens, regras de gameplay, site)    │
└───────────────────────────┬─────────────────────────────┘
                            │  Implementação
                            ▼
┌─────────────────────────────────────────────────────────┐
│               🎮 EXPERIÊNCIA DO JOGO / LIVRO            │
│          (Gameplay, diálogos, Tomo, cutscenes)          │
└─────────────────────────────────────────────────────────┘
```

---

## 2. Checklist de Consulta Pré-Escrita (Protocolo do Bibliotecário)

Antes de redigir qualquer novo capítulo, conto, diálogo ou ficha, consulte esta base para responder:

1. **"O que já sabemos sobre isso?"** *(Verificar fichas em `01-personagens/` e `05-regras-de-mundo/`)*
2. **"O que já aconteceu e quando?"** *(Verificar `02-cronologia/CRONOLOGIA_MESTRE.md`)*
3. **"Isso contradiz algum fato canônico anterior?"** *(Verificar restrições `[🟢 CANÔNICO]`)*
4. **"Esse personagem poderia saber disso neste momento?"** *(Verificar campos de conhecimento do personagem)*
5. **"Essa revelação estraga algum mistério não revelado?"** *(Verificar `03-segredos-e-revelacoes/MATRIZ_SEGREDOS.md`)*
6. **"Qual o impacto dessa alteração nas outras entidades?"** *(Verificar `04-mapa-relacoes/MAPA_RELACOES.md`)*

---

## 3. Matriz de Estados de Informação

Toda anotação neste banco deve conter classificação explícita:

| Tag | Estado | Significado e Regra |
| :--- | :--- | :--- |
| `[🟢 CANÔNICO]` | Canônico | Fato oficial aprovado pelo criador. Imutável sem ordem direta. |
| `[🟡 EM CONSTRUÇÃO]` | Em Construção | Elemento em desenvolvimento ativo; estrutura básica definida, detalhes móveis. |
| `[🟠 IDEIA]` | Ideia / Hipótese | Proposta narrativa para avaliação; não pode ser tratada como verdade. |
| `[🔴 DESCONHECIDO]` | Desconhecido | Lacuna não estabelecida no cânone; **PROIBIDO inventar para preencher**. |
| `[⚫ DESCARTADO]` | Descartado | Ideia rejeitada formalmente; mantida com justificativa para não retornar. |

---

## 4. Índice de Módulos do Banco

- `01-personagens/`: Fichas profundas com biografia, cronologia individual, matriz de conhecimentos e segredos.
- `02-cronologia/`: Linha temporal mestra estruturada em *Era → Período → Evento → Personagem → Consequência*.
- `03-segredos-e-revelacoes/`: Controle de visibilidade de informação (Mundo / Personagem / Autor / Jogador).
- `04-mapa-relacoes/`: Grafo de conexões entre personagens, linhagens, facções, locais e objetos.
- `05-regras-de-mundo/`: Metafísica, leis da magia, percepção temporal e fisiologia de entidades ancestrais.
