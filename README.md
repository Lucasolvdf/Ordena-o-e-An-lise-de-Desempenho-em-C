# Benchmark de Algoritmos de Ordenação ##

•Este repositório contém um programa em C que realiza o benchmark de três algoritmos clássicos de ordenação: Insertion Sort, Merge Sort e Quick Sort. O programa compara o desempenho dos algoritmos em diferentes tamanhos de vetores aleatórios, medindo o número de comparações, movimentações e o tempo de execução.

## Algoritmos Implementados
#### 1. Insertion Sort

O Insertion Sort é um algoritmo de ordenação simples, que insere os elementos em uma posição correta dentro de uma sublista ordenada. Ele tem um desempenho de O(n²) no pior caso, o que o torna ineficiente para listas grandes. No entanto, para listas pequenas ou quase ordenadas, ele pode ser eficiente.

#### 2. Merge Sort

O Merge Sort é um algoritmo de ordenação eficiente que utiliza a técnica de dividir e conquistar. Ele divide o vetor em subvetores menores e, em seguida, os ordena e os mescla. O Merge Sort tem um desempenho O(n log n) no pior caso, o que o torna muito eficiente, especialmente para listas grandes.

#### 3. Quick Sort

O Quick Sort é outro algoritmo de ordenação baseado em divisão e conquista. Ele escolhe um elemento como pivô e particiona o vetor em elementos menores e maiores que o pivô, recursivamente ordenando as duas partes. Seu desempenho médio é O(n log n), mas no pior caso pode ser O(n²), embora isso seja raro com uma boa escolha de pivô.

Os três algoritmos foram implementados para ordenar vetores de diferentes tamanhos e para medir o número de comparações, movimentações e tempo de execução.

 ### Como Compilar e Rodar
 Para compilar o código, você pode usar o compilador gcc:
 ```
gcc -O1 -std=c11 src/*.c -o ordena
 ```
Para rodar o programa:
 ```
./ordena
 ```
O programa irá executar os algoritmos de ordenação tanto para vetores pequenos, com saída passo a passo, quanto para vetores de tamanhos maiores, com resultados agregados.

## Política de Contagem de Passos
A contagem de passos (comparações e movimentações) segue os seguintes critérios:

• Comparações: Cada vez que dois elementos são comparados durante o processo de ordenação (ex: se um elemento é maior que outro).

• Movimentos: Cada vez que um elemento é movido ou trocado no vetor.

Essas métricas são coletadas para cada um dos três algoritmos e apresentadas tanto no final da execução quanto durante a execução dos algoritmos em vetores pequenos (para uma análise passo a passo).


## Método de Medição de Tempo

O tempo de execução é medido utilizando a função clock() da biblioteca padrão do C. O tempo é calculado em milissegundos e é registrado para cada execução de algoritmo. A medição do tempo é feita em três estágios para cada algoritmo:


1. #### Antes de executar o algoritmo.
2. #### Durante a execução do algoritmo.
3. #### Após a conclusão da execução do algoritmo

Os resultados de tempo são apresentados no formato de milissegundos (ms).

### Resultados

Os resultados são gerados para três diferentes tamanhos de vetor (100, 1000 e 10000) e são apresentados em formato CSV. Um exemplo de como o arquivo de saída será gerado:

 ```
Algoritmo,N,Comparações,Movimentos,Tempo (ms)
InsertionSort,100,234,123,0.234567
MergeSort,100,567,234,0.345678
QuickSort,100,123,456,0.123456
 ```

### Gráfico Opcional

Você pode gerar gráficos dos resultados utilizando ferramentas como Excel ou Python para importar o CSV e plotar os resultados de tempo, comparações e movimentos em função do tamanho do vetor.

### Discussão Crítica

#### Computabilidade vs Escalabilidade


• Insertion Sort é um algoritmo simples, mas sua complexidade de O(n²) torna-o impraticável para vetores grandes.


• Merge Sort tem uma complexidade mais eficiente de O(n log n) e funciona bem para listas grandes, mas a alocação de memória adicional pode ser um fator limitante.


• Quick Sort é geralmente mais rápido que o Merge Sort em média devido ao seu comportamento melhor em memória cache, mas pode cair para O(n²) no pior caso se o pivô não for bem escolhido.


### Limites Observados

Para vetores pequenos (até 1000 elementos), todos os algoritmos têm um desempenho razoável. No entanto, à medida que o tamanho do vetor cresce (por exemplo, 10.000 elementos), o Quick Sort e o Merge Sort tendem a ter um desempenho significativamente melhor que o Insertion Sort.

### Conclusão

• Merge Sort e Quick Sort são os algoritmos mais eficientes para vetores grandes devido ao seu desempenho O(n log n).

• Insertion Sort deve ser evitado para grandes volumes de dados devido à sua complexidade quadrática.

• O Quick Sort tende a ser o mais rápido em termos de tempo de execução para vetores de tamanho médio, mas o Merge Sort oferece maior garantia de desempenho em termos de estabilidade e eficiência.

## Notas Finais

Este repositório oferece uma análise empírica do desempenho de diferentes algoritmos de ordenação em função do tamanho do vetor. A execução e a coleta de métricas são feitas de forma a garantir resultados consistentes e comparáveis entre os algoritmos.
