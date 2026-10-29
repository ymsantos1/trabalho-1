# Etapa 8 — Funcionalidade adicional e revisão final

> Status: **planejada**

## Objetivo
Implementar pelo menos uma funcionalidade adicional e fazer a revisão final do projeto, incluindo o `README.md`.

## Funcionalidades adicionais planejadas
(escolhidas do rol de exemplos do enunciado — confirmar quais manter)
1. **Favoritos** — marcar/desmarcar contato como favorito (campo `favorito` já previsto no modelo); favoritos aparecem primeiro e/ou com destaque.
2. **Ordenação alfabética** — ordenar a lista por nome (A→Z).
3. **Contador de contatos** — total exibido em `#contador` (e, durante a busca, "X de Y").

> Mínimo exigido pelo enunciado: **uma** funcionalidade adicional. As três acima tornam o trabalho mais completo.

## O que será feito
- Botão/ícone de favorito em cada card; `alternarFavorito(id)` atualiza o array e persiste.
- Ordenação aplicada na renderização (favoritos primeiro, depois ordem alfabética).
- Contador atualizado em todas as operações.

## Revisão final
- Conferir todos os requisitos obrigatórios (cadastro, listagem, persistência, remoção, edição, busca, estado vazio).
- Revisar organização do JS (funções com responsabilidade única).
- Revisar responsividade e usabilidade.
- Escrever `README.md` com: descrição, funcionalidades, como executar, estrutura de arquivos e tecnologias.
- (Opcional) Commit e push para o repositório no GitHub.

## Como testar
Checklist completo dos requisitos do enunciado em `index.html`, em desktop e em tela pequena.

## Entregáveis
- Funcionalidades extras em `app.js`/`styles.css`.
- `README.md`.
- Esta documentação atualizada com o resultado.
