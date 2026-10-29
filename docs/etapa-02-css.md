# Etapa 2 — CSS e responsividade

> Status: **planejada**

## Objetivo
Estilizar a aplicação para uma interface organizada, legível e agradável, com bom comportamento em telas menores. Sem design complexo — foco em clareza.

## O que será feito
- Definir variáveis CSS (`:root`) para cores, espaçamentos e raio de borda.
- Tipografia e reset básico consistentes.
- **Layout:** formulário e lista lado a lado em telas grandes; empilhados (coluna única) no celular, usando Flexbox/Grid com `@media`.
- Estilizar os **painéis** (`.painel`) como cartões com sombra leve e espaçamento interno.
- **Formulário:** rótulos acima dos campos, campos com largura total, foco visível, espaçamento confortável.
- **Botões de ação** claros: primário (Adicionar/Salvar), secundário (Cancelar), e botões de editar/remover nos contatos.
- **Contatos em cards** (`.lista-contatos` como grid de cartões): nome em destaque, e-mail e telefone abaixo, botões de ação no canto.
- Estilizar o **campo de busca** e o **contador**.
- **Estado vazio** com estilo discreto (texto centralizado, cor suave).
- Acessibilidade visual: contraste adequado, foco de teclado visível.

## Critérios de qualidade
- Espaçamento e alinhamento consistentes.
- Interface legível em ~360px de largura (celular) sem rolagem horizontal.
- Botões com área de clique confortável.

## Como testar
Abrir `index.html` e redimensionar a janela (ou usar o modo responsivo do navegador) para verificar o comportamento em telas pequenas.

## Entregáveis
- `styles.css` completo.
- Esta documentação atualizada com o resultado.
