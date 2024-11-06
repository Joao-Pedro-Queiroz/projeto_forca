# Jogador Automático de Forca com Teoria da Informação

Este projeto consiste no desenvolvimento de um jogador automático de forca, com o objetivo de maximizar suas chances de vitória em um jogo de forca. O jogador implementado utiliza conceitos de teoria da informação para priorizar suas jogadas, garantindo decisões que maximizam a probabilidade de sucesso ao longo das tentativas.

## Objetivo

A meta principal é criar um jogador que ganhe o máximo de jogos possíveis com um limite de 5 vidas. Para isso, o algoritmo deve explorar a frequência das letras nas palavras do vocabulário fornecido e aplicar técnicas probabilísticas e de entropia, o que permite ao jogador otimizar suas escolhas e minimizar perdas de vida.

## Conceitos Utilizados: Teoria da Informação e Probabilidades

Para desenvolver um jogador de forca eficiente, aplicamos o conceito de entropia, da teoria da informação, para priorizar letras. A entropia mede a quantidade de incerteza ou surpresa em um conjunto de eventos possíveis. Aqui, utilizamos a entropia para identificar as letras que, ao serem escolhidas, reduzem a incerteza sobre a palavra secreta.

1. **Cálculo da Entropia**: Utilizamos a frequência de letras no vocabulário fornecido como base para calcular a entropia de cada letra. Quanto mais frequente a letra no vocabulário, menor a entropia associada a ela, já que sua escolha tende a ser menos surpreendente.
2. **Distribuição de Probabilidades**: Com base na entropia calculada, priorizamos letras que maximizem a informação obtida a cada jogada. Isso significa que, em vez de selecionar letras aleatoriamente, o jogador escolhe aquelas que reduzem a incerteza, aumentando as chances de acertar as letras presentes na palavra.

## Arquitetura do Projeto

- **JogoDeForca**: Esta classe define as regras do jogo e controla o número de vidas do jogador. Quando o jogador escolhe uma letra, o "juiz" (representado pela classe `JogoDeForca`) informa se a letra está correta e as posições em que aparece, ou diminui uma vida caso a letra esteja incorreta.
- **Jogador**: Implementa a lógica do jogador automático. Essa classe calcula a probabilidade de cada letra com base no vocabulário e utiliza a entropia para definir uma estratégia otimizada. Cada tentativa é baseada na escolha da letra com maior chance de reduzir a incerteza, levando em conta as tentativas já realizadas e o estado atual da palavra.

## Avaliação de Desempenho

Para avaliar o desempenho do jogador, executamos 100 jogos com palavras escolhidas aleatoriamente. Em cada jogo, o jogador utiliza sua estratégia de entropia para maximizar as chances de sucesso. Calculamos a taxa de vitória para determinar o sucesso da estratégia.

### Resultados Obtidos

Nos testes realizados, o jogador obteve uma taxa de vitória de aproximadamente **93%**, onde a quantidade de vitórias a cada execução tem uma mpedia de variação entre 90 e 96 vitórias de 100 partidas. Este resultado sugere que a aplicação da teoria da informação e das probabilidades é eficaz para melhorar a performance em um jogo de forca com 5 vidas limitadas.

## Análise de Casos de Erro

Embora a estratégia seja eficiente, há casos em que o jogador automático falha. Aqui estão as principais situações em que os erros ocorrem, junto com suas causas:

1. **Palavras com Letras Raras**: Em palavras que contêm letras pouco frequentes no vocabulário, o algoritmo tende a escolher letras comuns primeiro. Isso leva à perda de vidas ao adivinhar letras que estão ausentes na palavra.
2. **Palavras Curtas com Altas Entropias**: Palavras curtas oferecem menos oportunidades para corrigir escolhas incorretas. Em tais palavras, se o jogador perde algumas vidas ao tentar letras comuns que não estão na palavra, ele rapidamente se aproxima de uma derrota.
3. **Palavras com Padrões Incomuns**: Algumas palavras têm combinações de letras que são raras no vocabulário geral (por exemplo, palavras com muitas consoantes seguidas ou uma distribuição incomum de vogais). O algoritmo pode falhar nesses casos ao tentar letras improváveis para reduzir a incerteza, levando a tentativas infrutíferas e perdas de vida.

Essas análises são importantes para aprimorar futuras versões do jogador automático, adaptando-o para reconhecer padrões de palavras e ajustar sua estratégia quando as condições de erro forem detectadas.

## Uso e Demonstração

O notebook `demo.ipynb` contém todos os passos necessários para executar o jogador automático de forca, desde a importação do vocabulário até a execução de 100 partidas consecutivas. Cada célula do notebook está comentada para explicar o funcionamento do código e os resultados de cada fase.

### Instruções para Rodar o Projeto

1. Clone o repositório e acesse o diretório principal.
2. Execute o notebook `demo.ipynb` para ver a demonstração completa. O notebook já está executado, com todos os dados gerados, permitindo visualizar os resultados sem a necessidade de reexecução.

## Conclusão

Este projeto demonstra a eficácia do uso da teoria da informação aplicada a um jogo de forca. A estratégia de entropia permite que o jogador faça escolhas informadas, maximizando suas chances de sucesso. O jogador automático implementado é eficaz na maioria das vezes, mas há oportunidades de melhoria em casos onde a estrutura da palavra ou a frequência das letras se tornam desvantagens estratégicas.