---

B-TREE e HASH INDEX - Qual a diferença?
Hoje em dia, a maioria dos bancos de dados relacionais utiliza índices para melhorar a performance de consultas. Esses índices podem ser de duas formas: B-tree e Hash. Neste artigo, vamos entender a diferença entre eles e quando utilizar cada um.

---

O que é um índice?
Um índice é uma estrutura de dados que permite a busca de um registro em um arquivo de dados. Ele é composto por uma chave e um ponteiro para o registro correspondente. A chave é um valor que identifica o registro e o ponteiro é o endereço do registro no arquivo de dados.

---

O que é um índice B-Tree?
O índice B-Tree funciona como uma árvore binária de busca, onde cada nó pode ter no máximo um número fixo de filhos. A árvore é balanceada, ou seja, a diferença de altura entre os filhos de um nó não pode ser maior que 1. A árvore é balanceada através de operações de rotação e redistribuição.
Exemplo de um índice B-Tree:
Fonte: How Database B-Tree Indexing Works
Onde é utilizado?
O índice B-Tree é utilizado em bancos de dados relacionais, como o MySQL, PostgreSQL, Oracle, etc. Ele é utilizado para otimizar a busca de registros em tabelas.
Devido a sua estrutura, o índice B-Tree é utilizado para buscas de registros que contenham valores de chaves próximas.
Dessa forma, fica mais fácil encontrar um registro que contenha a chave 100, do que um registro que contenha a chave 1000000, por exemplo.

---

O que é um índice Hash?
O índice Hash funciona como uma tabela de dispersão, onde cada chave é mapeada para um valor de dispersão. O valor de dispersão é um número que indica a posição do registro no arquivo de dados.
Talvez você esteja se perguntando: "Mas como o índice Hash funciona se não é uma árvore?". Bom, o índice Hash funciona como uma árvore, mas a árvore é virtual. Ou seja, a árvore não é armazenada em memória, mas sim o índice Hash.
Funciona assim: cada nó da árvore é um índice Hash. Cada índice Hash é um vetor de ponteiros para os registros. O índice Hash é um vetor de tamanho fixo, onde cada posição do vetor é um ponteiro para um registro. O valor de dispersão é o índice do vetor.
O Index Hash é como se fosse uma função, onde cada chave é mapeada para um valor de dispersão. Esse valor de dispersão é o índice do vetor de ponteiros.
Exemplo de um índice Hash:
Fonte: All About Indexes, Part 2: MySQL Index Structure and Performance
Onde é utilizado?
O índice Hash é utilizado em bancos de dados não relacionais, como o MongoDB, Redis, etc. Ele é utilizado para otimizar a busca de registros em tabelas, porém, também é utilizado em bancos de dados relacionais, como o MySQL, PostgreSQL, Oracle, etc.
Devido a sua estrutura, o índice Hash é utilizado para buscas de registros que contenham valores de chaves aleatórias.

---

Qual a diferença entre o índice B-Tree e o índice Hash?
O índice B-Tree é utilizado para buscas de registros que contenham valores de chaves próximas, enquanto o índice Hash é utilizado para buscas de registros que contenham valores de chaves aleatórias.
O índice B-Tree é uma árvore binária de busca, enquanto o índice Hash é uma tabela de dispersão.
O índice B-Tree é utilizado em bancos de dados relacionais, enquanto o índice Hash é mais utilizado em bancos de dados não relacionais.
O Index Hash fica armazenado em memória, enquanto o índice B-Tree fica armazenado em disco.

---

Referências
All About Indexes, Part 2: MySQL Index Structure and Performance
How Database B-Tree Indexing Works
