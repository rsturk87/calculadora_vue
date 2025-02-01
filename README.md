# Calculadora Aritmética com VueJS

Este é um projeto simples de uma calculadora aritmética desenvolvido com VueJS. A aplicação permite que o usuário insira dois números, selecione uma operação (adição, subtração, multiplicação ou divisão) e visualize o resultado do cálculo automaticamente, sem a necessidade de clicar em botões adicionais.

## Funcionalidades

- **Entrada de Valores:**  
  Permite inserir os números A e B.

- **Seleção de Operação:**  
  O usuário pode escolher a operação aritmética desejada através de um campo do tipo _select_.

- **Cálculo Automático:**  
  O resultado é calculado e exibido automaticamente sempre que algum dos valores ou a operação é alterada.

- **Modo Escuro:**  
  Possibilidade de alternar entre modo claro e escuro, com a preferência sendo salva no `localStorage`.

## Estrutura do Projeto

O projeto é composto por três componentes principais:

- **Cabecalho:**  
  Exibe o título da aplicação.

- **Calculadora:**  
  Contém os campos de entrada para os números e o _select_ para escolher a operação.

- **Resultado:**  
  Exibe o resultado do cálculo realizado.

Além desses componentes, o `App.vue` centraliza a lógica do estado da aplicação, a comunicação entre os componentes e a implementação do modo escuro.

## Tecnologias Utilizadas

- [VueJS 3](https://vuejs.org/)
- JavaScript (ES6+)
- CSS

## Como Executar o Projeto

### Pré-requisitos

- [Node.js](https://nodejs.org/) (recomenda-se a versão LTS)
- [npm](https://www.npmjs.com/) ou [Yarn](https://yarnpkg.com/)

### Passos para Instalação

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
