# aula04
## SELECT: expressões aritméticas, valores nulos, inclusão de literais, DISTINCT, ORDER BY

[0. Requisitos](#0-requisitos)

[1. Expressões Aritméticas](#1-expressões-aritméticas)

[2. Valores Nulos](#2-valores-nulos)

[3. Inclusão de Literais](#3-inclusão-de-literais)

[4. DISTINCT](#4-distinct)

[5. ORDER BY](#5-order-by)

[Bibliografia e Referências](#bibliografia-e-referencias)

[Outros](#outros)

## 0. Requisitos
Requisitos: Para esta aula, precisa de ter o ambiente de trabalho configurado ([Docker](https://www.docker.com/products/docker-desktop/) com [base de dados HR](https://github.com/ULHT-BD/aula03/blob/main/docker_db_aula03.zip) e [DBeaver](https://dbeaver.io/download/)). Caso ainda não o tenha feito, veja como fazer seguindo o passo 1 da [aula anterior](https://github.com/ULHT-BD/aula03/edit/main/README.md#1-prepare-o-seu-ambiente-de-trabalho).

Caso já tenha o docker pode iniciá-lo usando o comando ```docker start mysgbd``` no terminal, ou através do interface gráfico do docker-desktop:
<img width="1305" alt="image" src="https://user-images.githubusercontent.com/32137262/194916340-13af4c85-c282-4d98-a571-9c4f7b468bbb.png">

Deve também ter o cliente DBeaver.

## 1. Expressões Aritméticas
O operador SELECT permite efetuar operações aritméticas entre escalares e/ou atributos. A sintaxe é:
``` sql
SELECT expressão operador expressão, ...
FROM relacao;
```
onde uma expressão pode ser um atributo, mas também uma variável ou uma constante, e o operador pode ser ```+``` (adição), ```-``` (subtração), ```*``` (multiplicação), ```/``` (divisão) ou ```%``` (resto da divisão inteira). Exemplo:
* Que idade terão os estudantes após os 3 anos de curso
``` sql
SELECT nome, idade, idade + 3 AS idade_finalista
FROM estudante;
```
NOTA: ```idade + 3 AS idade_finalista``` permite renomear o nome da coluna ```idade + 3``` em ```idade_finalista```. Podemos ainda, para simplificar, omitir a palavra ```AS``` e escrever ```idade + 3 idade_finalista```

### Exercícios
Para cada uma das alíneas seguintes, escreva a query que permite obter:
1. O resultado da operação ```2 + 3 * 25```

2. Para cada posição (job), o nome da posição, salário mínimo, máximo e o range salarial, diferença entre o salário máximo e o salário mínimo

3. Para cada empregado, o seu primeiro nome, o valor do seu salário atual e do salário após aumento de 5% e salário com aumento de 10%


## 2. Valores Nulos
Em SQL, o valor ```NULL``` é utilizado para representar um campo vazio, sem qualquer valor. Numa dada relação, se um atributo for opcional e se adicionamos um tuplo sem especificar um valor é atribuido o valor ```NULL```. ```NULL``` é diferente do valor ```0``` ou de uma string vazia ```''```

Em SQL existem funções próprias para testar e manipular o valor ```NULL```
* ```IS NULL```, 1 se o valor do atributo for ```NULL``` ou 0 caso contrário
``` sql
SELECT nome FROM estudante WHERE idade IS NULL;
```
* ```IS NOT NULL```, 1 se o valor do atributo não for ```NULL``` ou 0 caso contrário
``` sql
SELECT nome FROM estudante WHERE idade IS NOT NULL;
```
* ```IFNULL()``` retorna valor alternativo caso seja ```NULL```
``` sql
SELECT IFNULL(idade, 20) FROM aluno;
```
* ```COALESCE()``` retorna o primeiro valor não ```NULL``` de uma lista
``` sql
SELECT COALESCE(NULL, NULL, 'Base de Dados', NULL, 'Universidade Lusófona');
```

### Exercícios
Para cada uma das alíneas seguintes, escreva a query que permite obter:
1. Quais os departamentos que não possuem um Manager?

2. Quais os empregados que recebem uma percentagem de comissão (COMISSION_PCT)

3. Lista de todos os empregados e respetivas comissões, mostrando ```0``` sempre que esta é ```NULL```

4. Qual o primeiro valor não ```NULL``` da lista (NULL, 'Lisboa', 'Porto', NULL, 'Braga')

## 3. Inclusão de Literais
https://www.geeksforgeeks.org/sql-literals/
O operador SELECT permite efetuar operações aritméticas entre escalares e/ou atributos. A sintaxe é:
``` sql
SELECT expressão operador expressão, ...
FROM relacao;
```
onde uma expressão pode ser um atributo, mas também uma variável ou uma constante, e o operador pode ser ```+``` (adição), ```-``` (subtração), ```*``` (multiplicação), ```/``` (divisão) ou ```%``` (resto da divisão inteira). Exemplo:
* Que idade terão os estudantes após os 3 anos de curso
``` sql
SELECT nome, idade, idade + 3 AS idade_finalista
FROM estudante;
```
NOTA: ```idade + 3 AS idade_finalista``` permite renomear o nome da coluna ```idade + 3``` em ```idade_finalista```. Podemos ainda, para simplificar, omitir a palavra ```AS``` e escrever ```idade + 3 idade_finalista```

### Exercícios


## 4. DISTINCT
O operador DISTINCT permite obter apenas valores distintos/diferentes, i.e. permite remover duplicados.
NOTA: relembre que SQL duplicados podem existir uma vez que é baseado na teoria de sacos de tuplos (duplicados não existiriam na teoria dos conjuntos)

A sintaxe é:
``` sql
SELECT DISTINCT atributo, ...
FROM relacao;
```
Exemplo:
* Quais as diferentes idades dos estudantes
``` sql
SELECT DISTINCT idade
FROM estudante;
```

### Exercícios


## 5. ORDER BY
O operador ORDER BY permite ordenar os resultados segundo um ou mais atributos.
Por defeito os resultados são ordenados por ordem ascendente, mas podemos definir ordem descendente utilizando ```DESC```

A sintaxe é:
``` sql
SELECT atributo, ...
FROM relacao
ORDER BY atributo;
```

Exemplo:
* Obter nome de alunos ordenados por ordem decrescente de idade
``` sql
SELECT nome, idade
FROM estudante
ORDER BY idade DESC;
```

### Exercícios


## Bibliografia e Referências
* [w3schools - SQL Operators](https://www.w3schools.com/sql/sql_operators.asp)
* [w3schools - NULL values](https://www.w3schools.com/sql/sql_null_values.asp)
* [w3schools - DISTINCT](https://www.w3schools.com/sql/sql_distinct.asp)
* [w3schools - ORDER BY](https://www.w3schools.com/sql/sql_orderby.asp)

## Outros
Para dúvidas e discussões pode juntar-se ao grupo slack da turma através do [link](https://join.slack.com/t/ulht-bd/shared_invite/zt-1h783xcc2-eRQlIYSqFkDeOAqGC045Rw)
