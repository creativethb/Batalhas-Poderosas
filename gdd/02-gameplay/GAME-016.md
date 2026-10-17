---
id: "GAME-016"
nome: "Avatares-base e Personalização de Personagem"
status: "PLANEJADO"
funcao: "Arquitetura futura de aparência dos personagens jogáveis e cosméticos"
relacionados:
  - "GAME-014"
  - "NPC-014"
  - "DOS-004"
atualizado_por: "ChatGPT"
data_atualizacao: "2026-10-17"
---

# Avatares-base e Personalização de Personagem

> **DIREÇÃO DE DESIGN REGISTRADA EM 17/10/2026. NÃO IMPLEMENTADO.** O trabalho atual de otimização do modelo de John não é uma autorização para implementar o editor de personagem, substituir avatares em produção ou comercializar cosméticos.

## 1. Intenção

John, cuja referência visual foi fornecida pelo criador, será a aparência inicial/padrão de referência para a campanha Solo durante o desenvolvimento. O modelo atual está em otimização para uso 3D e animação. A personalização será introduzida futuramente, sem comprometer o papel narrativo de John; como a identidade visual personalizável conviverá com a identidade canônica do protagonista será detalhado antes da implementação.

Criar futuramente **duas malhas corporais-base**, uma masculina e uma feminina, para receber opções cosméticas, sem gerar um personagem completo para cada combinação. As duas devem ser compatíveis com o sistema de animação, equipamentos e rig adotado pelo projeto (R15 como referência de desenvolvimento, sujeito à validação técnica).

## 2. Opções desejadas

- Variações de olhos, nariz, boca, cabelo e demais traços faciais.
- Opções de aparência e tons de pele, respeitando a identidade artística estilizada do jogo.
- Conjunto inicial de roupas e peças intercambiáveis, com possibilidade de ampliação posterior.
- Quantidade de opções, interface, regras de combinação, proporções corporais e métodos técnicos **a definir**.

**Não fixar antecipadamente a implementação:** cabelo/acessórios podem ser malhas separadas; olhos/boca podem ser texturas ou componentes; nariz e formato do rosto podem exigir alternativas técnicas. Comparar soluções de desempenho, animação, clipping, compatibilidade de equipamentos e manutenção antes de escolher.

## 3. Compatibilidade com jornadas e perfil

**Proposta de integração, a validar na etapa técnica:** a aparência escolhida é vinculada à jornada individual e restaurada ao carregar seu slot, sem misturar personalizações entre as três jornadas. A identidade Roblox e as conquistas globais permanecem no escopo da conta conforme GAME-014. Partida Livre e eventuais predefinições compartilhadas ainda exigem decisão.

Nenhuma mudança em saves ou migração de dados está autorizada por este documento.

## 4. Cosméticos futuros e monetização

Preparar a arquitetura para um catálogo de cosméticos opcionais, inclusive roupas e skins pagas **após publicação**, sem ativar compras agora. Não definir preços, moedas premium, catálogo comercial, permissões de uso, repasses, inventário de compras ou serviços Roblox sem projeto e validação próprios. Priorizar itens visuais que não concedam vantagem competitiva. A titularidade de cosméticos adquiridos deve ser projetada separadamente da aparência selecionada em cada jornada; não confundir compra global com equipamento do slot.

## 5. Ordem sugerida de desenvolvimento

1. **Agora:** finalizar a malha/rig/animações de John e validar poses e compatibilidade com equipamentos; não iniciar editor.
2. **Depois:** especificar e testar protótipos dos dois corpos-base e as técnicas de variação facial e cabelo.
3. **Em seguida:** catálogo gratuito inicial de opções e editor de aparência, com persistência e integração de interface.
4. **Mais tarde:** roupas e conjuntos adicionais, testes de compatibilidade, acessibilidade e desempenho em dispositivos móveis.
5. **Após decisão comercial:** avaliar itens cosméticos pagos e integração segura com os mecanismos oficiais de compra Roblox.

## 6. Critérios e pendências

- Validar formato de rig e separação de malhas antes de produção em lote; roupas não devem exigir refazer o corpo inteiro.
- Avaliar orçamento de geometria, texturas, memória e desempenho; **não tratar um número de polígonos ainda não auditado como limite oficial**.
- Preservar identidade de John, a cronologia do GDD, inventário/equipamentos e a independência das jornadas.
- Não declarar editor, avatares femininos, variações faciais ou loja de skins como existentes.
- Não alterar o Menu Principal nem iniciar sistemas de monetização sem solicitação específica.
