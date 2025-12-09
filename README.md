# Animais Fantásticos

Projeto front-end estático do curso de JavaScript da Origamid, focado em manipulação do DOM com módulos ES6. A página apresenta navegação suave entre seções, abas de conteúdo para os animais, FAQ em acordeão, menu dropdown e modal de login.

## Recursos principais
- Navegação interna com rolagem suave.
- Animações acionadas conforme a seção entra na janela de visualização.
- Troca de conteúdo por abas na seção de animais.
- FAQ com acordeão mantendo o primeiro item aberto por padrão.
- Modal de login que pode ser fechado ao clicar fora da caixa.
- Menu dropdown com fechamento automático ao clicar fora.

## Como executar
Como o projeto é totalmente estático, basta servir o `index.html` em um navegador:
1. Instale uma ferramenta de servidor local (ex.: [`serve`](https://www.npmjs.com/package/serve)).
2. Na raiz do projeto, execute `npx serve .` e acesse o endereço indicado (geralmente `http://localhost:3000`).

Também é possível abrir o arquivo `index.html` diretamente, mas o uso de um servidor facilita o carregamento dos módulos ES6.

## Estrutura
```
animais-fantasticos/
├── css/           # Estilos e utilitários
├── img/           # Imagens da página
├── js/            # Script principal e módulos de interação
├── docs/          # Documentação adicional
└── index.html     # Página principal
```

## Documentação
Consulte `docs/overview.md` para um guia completo dos módulos JavaScript e dicas de extensão do projeto.

## Licença
[MIT](LICENSE)
