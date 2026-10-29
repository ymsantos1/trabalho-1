# Etapa 1 — Estrutura do projeto e HTML semântico

## Objetivo
Montar o esqueleto da aplicação de página única com HTML semântico, contendo as três áreas exigidas: **formulário**, **busca** e **exibição dos contatos** (incluindo o estado vazio).

## O que foi feito
- Criada a estrutura de arquivos do projeto:
  - `index.html` — estrutura da página.
  - `styles.css` — stub (estilo completo vem na Etapa 2).
  - `app.js` — stub (lógica vem na Etapa 3).
  - `docs/` — documentação das etapas.
- Escrito o `index.html` com marcação semântica.

## Decisões de marcação
- `<header>`, `<main>`, `<footer>` e `<section>` para estrutura semântica.
- **Formulário de cadastro/edição** (`#form-contato`) com os campos obrigatórios e tipos HTML adequados:
  - `nome` → `type="text"` `required`
  - `email` → `type="email"` `required`
  - `telefone` → `type="tel"` `required`
- Campo oculto `#contato-id` (`type="hidden"`): guarda o id do contato em edição. Vazio = novo cadastro, preenchido = modo edição (usado nas Etapas 4 e 6).
- Botões de ação:
  - `#btn-salvar` — rótulo muda entre "Adicionar" e "Salvar" conforme o modo.
  - `#btn-cancelar` — começa com `hidden`, aparece só no modo de edição.
- **Área de busca**: `<input type="search" id="busca">` para o filtro em tempo real (Etapa 7).
- **Lista**: `<ul id="lista-contatos">` vazia — será preenchida dinamicamente a partir do array (Etapa 4). O DOM reflete os dados, não é a fonte de estado.
- **Estado vazio**: `<p id="estado-vazio">` com mensagem padrão, controlado via JS depois.
- **Contador** (`#contador`) com `aria-live="polite"` — base para a funcionalidade adicional (Etapa 8) e acessibilidade.
- `novalidate` no form para a validação ser tratada/combinada no JS nas etapas seguintes (mantendo os atributos `required` e tipos para semântica).

## Como testar
Abrir `index.html` no navegador. Deve aparecer o formulário, o campo de busca, o título "Contatos" com contador e a mensagem de estado vazio. Ainda sem estilo elaborado e sem funcionalidade — isso vem nas próximas etapas.

## Próxima etapa
Etapa 2 — CSS: layout, espaçamento, estilo dos botões e responsividade.
