# Etapa 6 — Edição de contatos

> Status: **planejada**

## Objetivo
Permitir editar um contato: carregar seus dados no formulário, indicar o modo de edição e salvar ou cancelar.

## O que será feito
- Botão "Editar" em cada card (com `data-id`), tratado por delegação de eventos.
- `iniciarEdicao(id)`:
  - Preenche o formulário com os dados do contato.
  - Coloca o `id` no campo oculto `#contato-id`.
  - Muda o rótulo do botão principal para **"Salvar"** e exibe o botão **"Cancelar"**.
  - Muda o título do painel para "Editar contato" (indicação visual do modo).
- Handler de `submit` passa a verificar `#contato-id`:
  - Vazio → cria novo contato (Etapa 4).
  - Preenchido → `editarContato(id)` atualiza o objeto no array, salva e re-renderiza.
- `cancelarEdicao()`:
  - Limpa o formulário, esvazia `#contato-id`, restaura o rótulo "Adicionar", oculta "Cancelar" e o título volta a "Novo contato".

## Regras
- O estado principal continua no array; o formulário é apenas entrada.
- Após salvar a edição: persistir e re-renderizar; voltar ao modo "novo".

## Como testar
Editar um contato, salvar e confirmar a alteração na lista e após recarregar. Testar o botão Cancelar (não deve alterar nada).

## Entregáveis
- `iniciarEdicao()`, `editarContato()`, `cancelarEdicao()` em `app.js`.
- Esta documentação atualizada com o resultado.
