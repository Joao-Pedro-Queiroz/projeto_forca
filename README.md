# Jogo de Forca Interativo

Este projeto implementa um jogo de forca interativo com uma simulação de jogador que usa probabilidade para adivinhar palavras. O jogo gerencia tentativas e calcula a melhor próxima jogada.

## Estrutura do Projeto

O projeto possui duas classes principais:

1. **JogoDeForca**: Representa o jogo, contendo a lógica para validar as tentativas e gerenciar vitória ou derrota.
2. **Jogador**: Implementa a estratégia do jogador, que usa uma análise probabilística para tentar a palavra da melhor forma.

### Classe `JogoDeForca`

A classe `JogoDeForca` controla a palavra a ser adivinhada, as tentativas e o estado do jogo:

- **Palavra Secreta**: Palavra que o jogador precisa adivinhar.
- **Tentativas**: Letras já tentadas pelo jogador.
- **Erros Máximos**: Número limite de erros antes da derrota.
- **Método `tentar_letra(letra)`**: Avalia se a letra está correta e atualiza o jogo.
- **Condições de Fim de Jogo**: O jogo termina quando a palavra é totalmente adivinhada ou o limite de erros é alcançado.

### Classe `Jogador`

A classe `Jogador` implementa uma lógica probabilística, escolhendo letras com base em sua frequência na língua portuguesa e nas letras já descobertas na palavra secreta.

1. **Probabilidade de Letras**: O jogador utiliza um vetor de frequência de letras. A probabilidade de escolher uma letra é calculada dividindo a frequência da letra pela soma das frequências de todas as letras não tentadas.

2. **Seleção da Letra**: A cada rodada, a letra com maior probabilidade entre as não tentadas é escolhida.

### Condições de Vitória e Derrota

- **Vitória**: O jogador vence ao adivinhar todas as letras da palavra antes de atingir o limite de erros.
- **Derrota**: Se o limite de erros é atingido, o jogo exibe uma mensagem de perda e revela a palavra.  
  - **Casos de Derrota**: A derrota pode ocorrer se o jogador escolher muitas letras comuns que não estão na palavra específica, desperdiçando tentativas. Isso é mais provável quando a palavra contém letras raras, o que leva a uma sequência de erros.

### Estatísticas

A classe `Jogador` exibe estatísticas ao final das rodadas, permitindo ajustar estratégias em novas tentativas.

## Como Jogar

Execute o script principal para iniciar o jogo, e o jogador automático tentará adivinhar a palavra.
