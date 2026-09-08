# ⚔️ Batalhas Poderosas

[!["Status do Projeto"](https://img.shields.io/badge/Status-Em%20Desenvolvimento-orange?style=for-the-badge)](https://github.com/creativethb/Batalhas-Poderosas)
[!["Engine"](https://img.shields.io/badge/Engine-Roblox%20Studio-blue?style=for-the-badge)](https://github.com/creativethb/Batalhas-Poderosas)
[!["Framework"](https://img.shields.io/badge/Ferramenta-Rojo-red?style=for-the-badge)](https://github.com/creativethb/Batalhas-Poderosas)

**Batalhas Poderosas** é um RPG de Ação e Fantasia Medieval em 3D desenvolvido no Roblox Studio.

O jogo acompanha a saga de **John**, um jovem soldado residente na pacífica **Vila de Arkham**, parte do **Reino de Arkan**. Inicialmente inexperiente e frágil, John precisa treinar, coletar recursos básicos, forjar sua primeira arma e evoluir passo a passo para proteger sua vila. Em determinado momento, um confronto com uma força esmagadoramente superior o transportará para outro mundo, de onde ele deverá encontrar uma chave de retorno e voltar incomparavelmente mais poderoso.

> 🌍 *"A verdadeira história do Rei Mago e do antigo rei de Arkan foi perdida ou intencionalmente distorcida. Nas minas e relíquias de Arkham, as mentiras se revelam."*

---

## 🎮 Game Design & Pilares

- **Exploração e Interação:** A Vila de Arkham é o centro da vida comunitária, recheada de NPCs com 20 rotas territoriais próprias, sistema de diálogo imersivo e arquitetura responsiva construída programaticamente.
- **Preparação e Crafting:** O jogador não começa herói. A jornada flui desde coletar Madeira Comum na mesa de sua própria casa e Madeira Sagrada no bosque do Ancião Eldrin, até a forja milenar com Mestre Cedric.
- **Sistemas Multiplataforma:**
  - Gamepad, PC e Mobile totalmente mapeáveis e suportados nativamente (HUDs dinâmicos de exploração e combate).
  - Controle de Câmera Cinematográfica ("Over-the-shoulder") em interações cruciais.
  - Combate visceral encadeado (combo de 5 hits de Espada), lock-on automático e locomoção mista (corrida unificada ao dash + pulo duplo físico).

---

## 🛠️ Tecnologias e Ferramentas

O desenvolvimento técnico ocorre de forma moderna e programática, com foco absoluto em componentes orientados a eventos e design limpo:

| Componente | Ferramenta / Arquitetura | Status |
| :--- | :--- | :--- |
| **Engine & Mundo** | Roblox Studio | ✅ Ativo |
| **Controle de Versão** | Rojo + Git (`default.project.json`) | ✅ Ativo |
| **Sistemas NPCs** | Componentes Modulares + IA Situacional | ✅ Implementado |
| **Diálogos** | Módulos Dinâmicos Tipados em Luau | ✅ Implementado |
| **Modelagem 3D** | Meshes Geradas IA + Modulares R15 | ✅ Em Produção |

---

## 📂 Estrutura do GDD

O Game Design Document vive neste repositório:

```text
├── index.html           # Arquivo principal (GitHub Pages)
├── assets/              # Artes conceituais, mapas e screenshots do Studio
└── gdd/
    ├── 01-lore/         # Lenda do Rei Mago, a Saga de John e a História de Arkan
    ├── 02-gameplay/     # Sistemas de Diálogo, Combate, Pulo Duplo, HUD Contextual
    ├── 03-npcs/         # O Codex de Arkham: Mestre Cedric, Ancião Eldrin, Rowan
    ├── 04-itens/        # Banco de Itens: da Madeira Comum à Espada Sagrada
    ├── 05-locais/       # Fichas da Vila: Casa do John, Padaria, Mina, Oficina
    └── 99-canon/        # Diretrizes irrevogáveis de Design e Narrativa
```
