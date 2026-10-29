# Etapa 5 — Remoção de contatos

> Status: **concluída**

## Objetivo
Permitir remover um contato, atualizando o array, o Local Storage e a interface.

## O que será feito
- Botão "Remover" em cada card (já criado na Etapa 4), com `data-id`.
- `removerContato(id)` — filtra o array removendo o contato com o `id` informado, salva e re-renderiza.
- Associação dos eventos de clique:
  - Preferência por **delegação de eventos** no container `#lista-contatos` (um único listener que identifica o card pelo `data-id`), evitando re-registrar listeners a cada render.
- Confirmação antes de remover (`confirm()`), para evitar remoção acidental.

## Regras
- Após remover: `salvarContatos()` + `renderizarLista()` + `atualizarContador()` + `atualizarEstadoVazio()`.
- Se o contato removido estava em edição, o formulário volta ao modo "novo" (tratado junto à Etapa 6).

## Como testar
Remover um contato, recarregar a página e confirmar que ele não volta (persistência atualizada). Remover todos e verificar o estado vazio.

## Resultado
Implementado em `app.js`:
- `removerContato(id)` — `contatos.filter()` remove pelo id, depois `salvarContatos()` + `renderizarLista()` (que já atualiza contador e estado vazio).
- `aoClicarNaLista(evento)` — **delegação de eventos**: um único listener em `#lista-contatos` usa `closest("button[data-acao]")` e o `data-id` do card. Trata a ação "remover" com `confirm()` (a ação "editar" entra na Etapa 6).
- Listener registrado uma vez em `iniciar()` (não re-registra a cada render).

### Teste funcional (navegador)
- Cadastrados Ana, Bruno, Carla → remover Bruno → sobra [Ana, Carla], contador "2 contatos", Local Storage atualizado. ✅
- Cancelar a remoção (confirm = não) → nada é removido. ✅
- Remover todos → mensagem de estado vazio reaparece, contador "0 contatos". ✅

## Entregáveis
- `removerContato()` e delegação de eventos em `app.js`. ✅
- Esta documentação atualizada com o resultado. ✅
