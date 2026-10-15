# Manutenção do GDD por entrega

O GDD deve acompanhar o desenvolvimento sem depender de reconstrução de memória de um chat.

## Ao terminar uma alteração relevante no jogo

1. Atualizar o acompanhamento local `GDD_ACOMPANHAMENTO.md` na raiz do workspace: data, entrega, sistemas/arquivos reais, fichas afetadas, evidências, testes realizados e pendências. Não guardar credenciais ou dados pessoais de jogadores.
2. Distinguir IMPLEMENTADO, TESTADO no cenário descrito, VALIDADO pelo responsável e PLANEJADO. Um pedido, ID configurado ou teste estático não comprova funcionamento completo.
3. Preparar o texto documental junto ao relatório da entrega. Corrigir a descrição vigente nas fichas e catálogos; não apenas anexar blocos contraditórios. Preservar histórico com data quando necessário.
4. Revisar o GDD ao concluir uma etapa funcional, antes de uma publicação autorizada ou quando o usuário pedir atualização. Mudanças pequenas podem ficar agrupadas na fila local, sem serem esquecidas.
5. Conferir o HEAD remoto e alterações locais antes de sincronizar. Nunca sobrescrever trabalho pendente com reset/pull indiscriminado; usar cópia isolada e backup quando necessário.
6. Atualizar fichas relacionadas, índice Markdown, manifesto quando necessário e changelog. Preservar IDs, cânone e referências; substituição de decisão segue protocolo próprio.
7. Verificar frontmatter, links, referências, ausência de credenciais e escopo do diff. **Não alterar index.html, renderizador ou arquitetura do site.** Nenhum teste de documentação autoriza modificar gameplay.
8. Registrar commit/hash e data da sincronização; marcar exatamente as entradas incluídas como sincronizadas. Se o envio falhar, manter estado AGUARDANDO SINCRONIZAÇÃO, sem afirmar que o GDD oficial mudou.

## Registro mínimo

| Campo | Conteúdo |
|---|---|
| Data / entrega | Identificação rastreável |
| Estado real | Implementado / teste limitado / planejado |
| Alterações reais | Scripts, objetos, configurações |
| Fichas afetadas | IDs e caminhos existentes |
| Evidência | Relatório/resultado/captura local |
| Testes e limites | Executado, estático e não executado |
| Texto preparado | Descrição atual sem funções futuras anunciadas como ativas |
| Sincronização | Pendente ou commit remoto confirmado |

Não existe agendamento automático criado por este documento. Push depende de autorização aplicável à entrega; publicar o jogo exige autorização específica. A Carteira da Guilda futura, multiplayer, aquisição do mapa e serviços não definidos continuam planejamento.
