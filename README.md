# aula04
## SELECT: expressões aritméticas, valores nulos, inclusão de literais, DISTINCT, ORDER BY

Requisitos: Para esta aula, precisa de ter o ambiente de trabalho configurado ([Docker](https://www.docker.com/products/docker-desktop/) com [base de dados HR](https://github.com/ULHT-BD/aula03/blob/main/docker_db_aula03.zip) e [DBeaver](https://dbeaver.io/download/)). Caso ainda não o tenha feito, veja como fazer seguindo o passo 1 da [aula anterior](https://github.com/ULHT-BD/aula03/edit/main/README.md#1-prepare-o-seu-ambiente-de-trabalho) 

[1. Expressões Aritméticas](#1-expressões-aritméticas)

[2. Valores Nulos](#2-valores-nulos)

[3. Inclusão de Literais](#3-inclusão-de-literais)

[4. DISTINCT](#4-distinct)

[5. ORDER BY](#5-order-by)

[Bibliografia e Referências](#bibliografia-e-referencias)

[Outros](#outros)

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

## 2. Valores Nulos
https://www.w3schools.com/sql/sql_null_values.asp
What is a NULL Value?
A field with a NULL value is a field with no value.

If a field in a table is optional, it is possible to insert a new record or update a record without adding a value to this field. Then, the field will be saved with a NULL value.

Note: A NULL value is different from a zero value or a field that contains spaces. A field with a NULL value is one that has been left blank during record creation!

How to Test for NULL Values?
It is not possible to test for NULL values with comparison operators, such as =, <, or <>.

We will have to use the IS NULL and IS NOT NULL operators instead.

https://www.w3schools.com/sql/sql_isnull.asp
Operadores IFNULL(), ISNULL(), COALESCE(), and NVL()
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
https://www.w3schools.com/sql/sql_distinct.asp
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


## 5. ORDER BY
https://www.w3schools.com/sql/sql_orderby.asp
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


## Bibliografia e Referências
* [w3resource - SQL Arithmetic Operators](https://www.w3resource.com/sql/arithmetic-operators/sql-arithmetic-operators.php)
* [w3schools - SQL Operators](https://www.w3schools.com/sql/sql_operators.asp)
* [javatpoint - SQL Arithmetic Operators](https://www.javatpoint.com/sql-arithmetic-operators)

## Outros
Para dúvidas e discussões pode juntar-se ao grupo slack da turma através do [link](https://join.slack.com/t/ulht-bd/shared_invite/zt-1h783xcc2-eRQlIYSqFkDeOAqGC045Rw)
