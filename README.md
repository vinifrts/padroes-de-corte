# otimização de cortes de bobinas com ortools

este projeto resolve um problema de otimização de cortes de bobinas utilizando programação linear inteira (pli) em python, com a biblioteca ortools.

a ideia é encontrar uma combinação de padrões de corte que atenda às demandas informadas, buscando minimizar o desperdício de material.

## como funciona

o programa recebe um arquivo `.txt` com o tamanho da bobina, a quantidade de tipos de itens e as demandas de cada tamanho.

a partir desses dados, ele:

- lê e valida os dados de entrada;
- gera os padrões maximais de corte possíveis;
- calcula a sobra de material de cada padrão;
- monta o modelo de programação linear inteira;
- utiliza o solver scip, disponibilizado pelo ortools, para encontrar a solução;
- mostra quantas bobinas devem ser cortadas usando cada padrão;
- calcula o total de bobinas utilizadas e o desperdício associado;
- mostra a quantidade total de cortes de cada tamanho.

## tecnologias utilizadas

- python
- ortools
- google colab

## formato do arquivo de entrada

o arquivo `.txt` deve conter os dados separados por espaços e linhas, seguindo este formato:

```text
150 3
80 70
60 100
50 120
```

a primeira linha contém o tamanho da bobina e a quantidade de tipos de itens.

as linhas seguintes contêm o tamanho de cada item e sua respectiva demanda.

no exemplo acima:

- `150 3`: bobina de 150 metros e 3 tipos de itens;
- `80 70`: 70 cortes de 80 metros;
- `60 100`: 100 cortes de 60 metros;
- `50 120`: 120 cortes de 50 metros.

## como executar

o projeto foi organizado para execução no google colab.

1. abra o notebook no google colab.
2. execute as células na ordem apresentada.
3. quando solicitado, envie o arquivo `.txt` com os dados de entrada.
4. aguarde o programa gerar os padrões e resolver o modelo.
5. confira os padrões escolhidos, o desperdício e o total de cortes por tamanho.

a biblioteca ortools é instalada pelo próprio notebook, então não é necessário configurar o ambiente manualmente antes de executar.

## exemplo de saída

para a entrada apresentada, a solução encontrada utiliza 125 bobinas e atende às demandas de:

- 70 cortes de 80 metros;
- 100 cortes de 60 metros;
- 120 cortes de 50 metros.

o desperdício associado à solução é de 1.150 metros.

o programa também exibe os padrões de corte utilizados, a quantidade de bobinas destinada a cada padrão e os excedentes de produção, quando existirem.

## observações

- o programa aceita diferentes tamanhos de bobinas, quantidades de tipos de itens e demandas, desde que o arquivo siga o formato esperado.
- os padrões gerados são maximais, ou seja, não permitem adicionar mais uma peça de nenhum dos tamanhos disponíveis sem ultrapassar o comprimento da bobina.
- a solução depende dos dados informados e dos padrões gerados pelo algoritmo.
- o desperdício associado considera tanto a sobra das bobinas utilizadas quanto o material correspondente às peças produzidas além da demanda, quando houver excedente.

## objetivo do projeto

este projeto foi desenvolvido para estudar a aplicação de programação linear inteira em um problema de corte unidimensional, utilizando o ortools para modelar as restrições e encontrar uma solução de otimização.
