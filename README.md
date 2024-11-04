
# Projeto Jogador de Forca

## Participantes
Vitor Raia e João Pedro Queiroz 

## Resumo

Este projeto implementa um jogo de forca interativo em Python, onde o jogador tenta adivinhar uma palavra escolhida aleatoriamente. A solução utiliza conceitos de **Teoria da Informação** e **Álgebra Linear** para otimizar a seleção das letras, explorando a compressão de dados através do algoritmo de Huffman. O projeto introduz duas classes principais: `JogoDeForca`, que gerencia as regras do jogo e controla as tentativas do jogador, e `Jogador`, que implementa uma estratégia automatizada para adivinhar palavras com base na frequência e posição das letras.

### Implementação e Conceitos Utilizados

1. **Teoria da Informação**: O projeto aplica o **algoritmo de Huffman** para calcular a frequência dos caracteres, otimizando a seleção das letras mais prováveis de aparecer na palavra. Esta abordagem, que utiliza árvores binárias de codificação, permite que o jogador simulado escolha letras que maximizam a informação adquirida a cada tentativa, reduzindo o número de tentativas necessárias para adivinhar a palavra completa.

2. **Álgebra Linear**: Os conceitos de álgebra linear auxiliam na manipulação de matrizes e vetores para estruturar e organizar os dados do jogo, como frequências e posições das letras, e para calcular distribuições probabilísticas das letras na palavra. Esse uso ajuda a otimizar as estratégias do jogador automatizado, facilitando a criação de uma estrutura que prioriza letras com maior probabilidade de ocorrer, com base em padrões linguísticos.

### Estrutura do Projeto

- `JogoDeForca`: Classe que gerencia o estado do jogo, controla o número de vidas, escolhe uma palavra aleatória e valida as tentativas do jogador.
- `Jogador`: Classe que implementa o jogador simulado, utiliza o algoritmo de Huffman para decidir a próxima letra a ser escolhida e monitora vitórias e derrotas.

### Execução

Para iniciar o jogo, basta instanciar as classes `JogoDeForca` e `Jogador`, e chamar o método `jogar` na instância de `Jogador`. Ao final das tentativas, o programa exibirá um gráfico de barras mostrando o número de vitórias e derrotas do jogador simulado.

