# Parser Recursivo-Descendente com Geração de AST

## Visão Geral

Este projeto é a implementação de um *Analisador Sintático (Parser)* para uma linguagem de programação simples, desenvolvido como parte da disciplina de Compiladores. O parser utiliza a abordagem recursivo-descendente para validar a estrutura do código-fonte, construir uma *Árvore Sintática Abstrata (AST)* e se recuperar de erros utilizando uma estratégia de *Modo Pânico*.

O programa não implementa um analisador léxico (lexer), consumindo diretamente uma lista de tokens pré-definidos.

## ✨ Funcionalidades Principais

- *Análise Recursivo-Descendente:* A estrutura do parser é baseada em um conjunto de funções mutuamente recursivas que representam as regras da gramática da linguagem.
- *Construção de AST:* Para cada instrução sintaticamente correta, uma Árvore Sintática Abstrata é construída, representando a estrutura hierárquica do código.
- *Modo Pânico para Recuperação de Erros:* Ao encontrar um erro de sintaxe, o parser é capaz de descartar tokens até um ponto de sincronização seguro (como ; ou }), permitindo que ele continue a análise e reporte múltiplos erros em uma única execução.
- *Visualização da AST:* O programa gera imagens no formato .png para cada AST construída, permitindo uma visualização clara da estrutura do código analisado.

## 📜 Gramática Suportada

O parser é capaz de analisar uma linguagem que inclui:

- *Declarações e Atribuições:* let var = expr; e var = expr;
- *Estruturas de Controle:* if-else e while
- *Retornos de Função:* return expr;
- *Blocos de Código:* Agrupamento de múltiplas instruções com { ... }
- *Expressões com Precedência de Operadores:*
  - Lógicos: ||, &&
  - Igualdade: ==, !=
  - Relacionais: <, <=, >, >=
  - Aritméticos: +, -, *, /
- *Operações Pós-fixas:* Chamada de função f(a, b) e acesso a índice arr[i].

## 🚀 Como Executar

1.  *Ambiente:* O projeto foi desenvolvido para ser executado em um ambiente como o *Google Colab* (main.ipynb).
2.  *Execução:* Abra o notebook main.ipynb e selecione a opção "Ambiente de execução" > "Executar tudo".
3.  *Resultados:*
    - A saída da suíte de testes será exibida na última célula.
    - As imagens .png das árvores sintáticas para os casos de teste válidos serão salvas em uma pasta chamada trees/.

## 🖼 Exemplo de Saída (AST)

Abaixo está um exemplo da Árvore Sintática Abstrata gerada para um comando if-else complexo:

*Código Fonte:*

if (x < 10 && y != 0) {
    x = x + 1;
} else {
    x = 0;
}


*AST Gerada:*

![Exemplo de AST para um comando if-else](/src/trees\case4_if_else_logic_stmt01.png)
