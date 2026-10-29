# Etapa 4 — Cadastro, listagem e estado vazio

> Status: **concluída**

## Objetivo
Permitir cadastrar contatos pelo formulário e exibi-los dinamicamente a partir do array, tratando o estado vazio.

## O que será feito
- `renderizarLista(lista)` — limpa `#lista-contatos` e recria os cards a partir do array recebido (por padrão, todos os contatos).
  - Cada card mostra nome, e-mail e telefone, e os botões de ação (editar/remover — ligados nas Etapas 5 e 6).
  - Usa o `id` do contato em `data-id` para as ações.
- `atualizarEstadoVazio(lista)` — mostra/oculta a mensagem `#estado-vazio` e ajusta o texto:
  - Sem contatos cadastrados: "Nenhum contato cadastrado ainda."
  - (Na Etapa 7) Busca sem resultados: "Nenhum contato encontrado."
- `atualizarContador()` — atualiza `#contador` com o total.
- Handler de `submit` do formulário:
  - `preventDefault()`, validação dos campos (obrigatórios + e-mail válido).
  - Cria o objeto contato, adiciona ao array (`adicionarContato()`), salva, re-renderiza e limpa o formulário.
- Garantir que, ao abrir a página, os contatos salvos sejam carregados e renderizados automaticamente.

## Regras
- A interface é sempre gerada a partir do array (re-render após cada mudança).
- Validação: nome não vazio, e-mail com formato válido, telefone não vazio.

## Como testar
Cadastrar alguns contatos, recarregar a página e confirmar que continuam aparecendo (persistência). Verificar a mensagem de estado vazio ao não haver contatos.

## Resultado
Implementado em `app.js`:
- Referências do DOM centralizadas no topo.
- `criarCardContato()` monta cada card com `document.createElement` e **`textContent`** (evita injeção de HTML); guarda o id em `data-id` e inclui os botões **Editar**/**Remover** (ligados nas Etapas 6 e 5).
- `renderizarLista(lista = contatos)` limpa o container e recria os cards a partir do array.
- `atualizarEstadoVazio()` mostra/oculta a mensagem conforme a lista.
- `atualizarContador()` exibe o total ("1 contato" / "N contatos").
- `obterDadosFormulario()` valida campos obrigatórios + e-mail (`checkValidity`).
- `adicionarContato()`, `aoEnviarFormulario()` (com `preventDefault`), `limparFormulario()`.
- `iniciar()` carrega o estado e renderiza ao abrir a página.

### Teste funcional (navegador, via servidor local)
- Estado inicial vazio: mensagem visível, contador "0 contatos". ✅
- Cadastro de 2 contatos → 2 cards, contador "2 contatos", estado vazio oculto. ✅
- IDs únicos gerados (2 ids distintos). ✅
- Local Storage reflete os contatos cadastrados. ✅
- **Persistência:** após recarregar a página, os 2 contatos voltam automaticamente. ✅

## Entregáveis
- Funções de render/cadastro em `app.js`. ✅
- Esta documentação atualizada com o resultado. ✅
