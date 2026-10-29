# Etapa 3 — Dados e persistência (Local Storage)

> Status: **concluída** (executada antes da Etapa 2 — o visual foi adiado para o final)

## Objetivo
Criar a camada de estado da aplicação: o array de contatos, o modelo de cada contato e as funções de persistência em Local Storage usando JSON.

## Modelo de contato
Cada contato é um objeto com identificador único:
```js
{
  id: "uuid-ou-timestamp",   // identificador único (usado em editar/remover)
  nome: "Maria Silva",
  email: "maria@email.com",
  telefone: "(11) 99999-9999",
  favorito: false            // usado na funcionalidade adicional (Etapa 8)
}
```

## Estado
- Variável única `contatos` (array de objetos) como **fonte de verdade**.
- O DOM reflete `contatos`; nunca o contrário.

## O que será feito
- Constante com a chave do Local Storage, ex.: `const CHAVE = "contatos";`.
- `carregarContatos()` — lê do Local Storage com `JSON.parse()`; retorna `[]` se não houver nada ou se o parse falhar (try/catch).
- `salvarContatos()` — grava o array com `JSON.stringify()`.
- `gerarId()` — gera identificador único (`crypto.randomUUID()` com fallback para `Date.now()`).
- Inicialização: ao carregar a página, `contatos = carregarContatos()`.

## Organização
Funções pequenas e com responsabilidade única, separadas da renderização e dos handlers de eventos.

## Como testar
No console do navegador, verificar que `localStorage.getItem("contatos")` reflete o array após operações (testado de fato a partir da Etapa 4).

## Resultado
Implementado em `app.js`:
- Constante `CHAVE_STORAGE = "contatos"` e estado `contatos = []` (fonte de verdade).
- `carregarContatos()` — lê e faz `JSON.parse()`, com `try/catch` retornando `[]` em caso de ausência/erro, e checagem `Array.isArray`.
- `salvarContatos()` — grava com `JSON.stringify(contatos)`.
- `gerarId()` — `crypto.randomUUID()` com fallback por tempo + aleatório.
- `iniciar()` em `DOMContentLoaded` carrega o estado salvo ao abrir a página (a renderização entra na Etapa 4).

Validação: `node --check app.js` sem erros de sintaxe. O teste funcional completo (gravar/recarregar visível) ocorre na Etapa 4, quando houver interface.

## Entregáveis
- Bloco de dados/persistência em `app.js`. ✅
- Esta documentação atualizada com o resultado. ✅
