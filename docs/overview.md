# Documentação do Projeto Animais Fantásticos

## Visão Geral
Este projeto recria a página "Animais Fantásticos" do curso de JavaScript da Origamid, explorando manipulação do DOM com módulos ES6. A interface apresenta uma lista de animais com conteúdo tabulado, FAQ em formato de acordeão, modal de autenticação e navegação suave entre sessões.

## Estrutura de Arquivos
- `index.html`: marcação principal da página e pontos de montagem para interações.
- `css/`: estilos da aplicação, incluindo grid, tipografia e classes utilitárias para estados ativos.
- `img/`: imagens utilizadas nas seções de animais e mapa de contato.
- `js/script.js`: arquivo de entrada que inicializa todos os módulos de comportamento.
- `js/modules/`: coleção de módulos JavaScript responsáveis por interações específicas.

## Guia dos Módulos JavaScript
Cada módulo utiliza seletores com atributos `data-*` definidos no HTML para acoplar comportamento sem depender de classes exclusivas.

### `scroll-suave.js`
- Seleciona links internos em `[data-menu="suave"]`.
- Intercepta cliques para aplicar `scrollIntoView` com `behavior: 'smooth'` até a seção alvo.

### `scroll-animacao.js`
- Observa elementos com `data-anime="scroll"`.
- Calcula quando cada seção cruza 60% da altura da janela (`window.innerHeight * 0.6`) e adiciona a classe `ativo` para animar a entrada.

### `nav-tab.js`
- Mapeia a lista de imagens `[data-tab="menu"]` com as descrições `[data-tab="content"]`.
- Na inicialização, ativa o primeiro conteúdo e, a cada clique no menu, troca a aba visível aplicando também a classe declarada em `data-anime`.

### `accordion.js`
- Conecta os títulos do FAQ (`dt`) marcados com `[data-anime="accordion"]`.
- Alterna a classe `ativo` no título e na respectiva resposta (`dd`) ao clique, mantendo o primeiro item aberto por padrão.

### `modal.js`
- Controla a abertura/fechamento do modal de login via elementos com `data-modal="abrir"`, `fechar` e `container`.
- Usa `classList.toggle('ativo')` para exibir o modal e fecha ao clicar fora da caixa de conteúdo.

### `dropdown-menu.js` e `outsideClick.js`
- Exibem o dropdown do menu superior em interações de clique ou toque.
- `outsideClick` registra listeners globais para fechar o menu quando o usuário interage fora do dropdown, removendo eventos após o encerramento.

## Executando o Projeto
Por ser um site estático, basta servir os arquivos HTML. Exemplos:
- Abrir `index.html` diretamente no navegador.
- Utilizar um servidor local com `npx serve` ou a extensão Live Server do VS Code para garantir o funcionamento de imports de módulos ES6.

## Como Estender
- **Adicionar novos animais**: inclua uma nova imagem em `[data-tab="menu"]` e uma nova `<section>` correspondente em `[data-tab="content"]`, definindo a animação desejada em `data-anime`.
- **Criar novas perguntas no FAQ**: acrescente pares `dt`/`dd` dentro de `.faq-lista` mantendo o atributo `data-anime="accordion"` no contêiner.
- **Novos gatilhos de modal**: qualquer elemento com `data-modal="abrir"` poderá abrir a janela, reaproveitando a lógica existente.
