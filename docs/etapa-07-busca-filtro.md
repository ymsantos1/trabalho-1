# Etapa 7 — Busca e filtro em tempo real

> Status: **planejada**

## Objetivo
Filtrar a lista em tempo real conforme o usuário digita, considerando pelo menos nome e e-mail, ignorando maiúsculas/minúsculas.

## O que será feito
- `filtrarContatos(termo)` — retorna os contatos cujo **nome** ou **e-mail** contêm o termo.
  - Normaliza com `.toLowerCase()` (e `.trim()` no termo) para ignorar caixa.
- Listener de `input` no campo `#busca`:
  - A cada tecla, calcula a lista filtrada e chama `renderizarLista(listaFiltrada)`.
- Integração com o estado vazio:
  - Busca sem resultados → mensagem "Nenhum contato encontrado." (diferente de "Nenhum contato cadastrado ainda.").
- O contador pode refletir "X de Y" durante a busca (a definir na Etapa 8).

## Regras
- A busca não altera o array; apenas a visualização é filtrada.
- Operações de editar/remover continuam funcionando sobre os cards filtrados (usam `id`).

## Como testar
Com vários contatos, digitar parte de um nome ou e-mail em diferentes caixas (maiúscula/minúscula) e verificar o filtro instantâneo. Buscar algo inexistente e ver a mensagem de "sem resultados".

## Entregáveis
- `filtrarContatos()` e o listener de busca em `app.js`.
- Esta documentação atualizada com o resultado.
