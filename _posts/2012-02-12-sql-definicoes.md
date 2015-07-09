---
layout: post
comments: false
title: "SQL definições"
excerpt: "SQL (Structured Query Language) como sabem é a Linguagem de Consulta Estruturada"
date: 2012-02-12 15:00:00
mathjax: true
published: true
---

# SQL definições

---

SQL (Structured Query Language) como sabem é a Linguagem de Consulta Estruturada, que é utilizada em bancos de dados relacionais, como MySQL, SQL Server, Postgre SQL,  
Firebird, Oracle e entre muitos outros bancos de dados existentes no mercado.

O SQL é muito parecido em utilização em todos os bancos de dados, porém não é igual em todos, cada fabricante ou mantenedor do banco de dados implementa o seu  
próprio SQL conforme desejar, geralmente o SQL ANSI é aceito por todos os bancos, ou seja, todos os bancos de dados partem do SQL ANSI para começar implementar  
suas melhorias.

SQL em si não é o SQL utilizado para codificação dentro do banco de dados, nestes casos, a intervenção do fabricante é forte e são implementadas as próprias  
funcionalidades e criada a sua própria linguagem, claro que como tudo vem do SQL ANSI, tudo é mais ou menos parecido, porém por exemplo na declaração de variáveis,  
implementação de laços, nestas capacidades é que são bastante diferenciadas, até porque, é o momento onde começa a se tornar uma linguagem de programação e não  
mais somente de consulta de dados, como a Microsoft por exemplo tem o T-SQL (Transact-SQL), a Oracle possui o PL/SQL (Procedural Language/Structured Query Language ).  

O SQL em si é dividido em subgrupos que basicamente seriam: DDL, DML, DQL, DCL e DTL

Dentro destes subgrupos, temos apenas alguns comandos do SQL, a divisão, é feita conforme a utilização que o comando tem como definida.

<strong>DDL - Data Definition Language (Linguagem de definição de dados)</strong>

A DDL tem como função, definir dados, essa definição se dá pelos três comandos abaixo descritos.

<ul>
    <li>CREATE - Permite criar objetos, como: banco de dados, tabelas, índices e views</li>
    <li>ALTER - Permite alterar objetos, como por exemplo, renomear um banco de dados, renomear tabelas, adicionar colunas em tabelas...</li>
    <li>DROP -  Permite excluir um objeto, você pode excluir um banco de dados, uma tabela, um índice e uma view, isso claro se o seu usuário tiver direitos para realizar a operação.</li>
</ul>

<strong>DML - Data Manipulation Language (Linguagem de manipulação de dados)</strong>

A DML tem como função manipular dados, este grupo é formado pelos três comandos abaixo descritos.

<ul>
    <li>INSERT - Permite inserir dados em tabelas, na realidade em cada insert é inserido um novo registro na tabela, onde os valores do registro devem ser passados no momento da inserção.</li>
    <li>UPDATE - Permite atualizar os dados de um registro, atulizar neste caso também inclui alterar dados de um registro.</li>
    <li>DELETE - Permite que você exclua um registro inteiro, não permite a exclusão de valores, apenas a exclusão de registros inteiros, para excluir valores você deve usar o comando UPDATE e passar o valor vazio ou nulo como desejar.</li>
</ul>

<strong>DCL - Data Control Language (Linguagem de Controle de Dados)</strong>

A DCL é utilizada basicamente para permitir ou negar que um determinado utilizador ou grupos ou seja lá como se chame no banco que está utilizando, tenha acesso à recursos do banco de dados e se dá basicamente pelos dois comandos abaixo citados.

<ul>
    <li>GRANT - Permite a utilização de determinados recursos, para determinados utilizadores.</li>
    <li>REVOKE - Restringe ou nega a utilização de determinados recursos para determinados utilizadores.</li>
</ul>

<strong>DTL - Data Transaction Language (Linguagem de Transação de Dados)</strong>

A DTL implementa a funcionalidade de transações, essas que permitem aprovar todas as modificações ou voltar ao estado que estava antes das modificações de uma vez só, isso garante a integridade do banco de dados quanto a falhas (Não tem nada com integridade relacional por aqui), pois quando dentro de uma operação grande ou mesmo de apenas dois comandos, se houver alguma falha você pode anular toda a operação e voltar ao estado anterior com o ROLLBACK, ou então se ocorrer tudo bem, você pode confirmar a operação com o COMMIT, os comando que implementam este grupo são basicamente os seguintes:

<ul>
    <li>START TRANSACTION - Inicia uma transação</li>
    <li>COMMIT - Confirma a operação inteira.</li>
    <li>ROLLBACK - Anula a operação inteira e volta ao estado anterior.</li>
</ul>

<strong>DQL - Data Query Language (Linguagem de Consulta de Dados)</strong>

Por último mas não menos importante, existe a DQL que é composta apenas pelo comando SELECT, porém existem cláusulas que são utilizadas junto com o SELECT, vejamos abaixo.

<ul>
    <li>SELECT - É um comando de projeção de dados, permite determinar as colunas que devem ser retornadas na consulta.</li>
</ul>

<strong>Cláusulas</strong>

<ul>
    <li>FROM - Indica a tabela alvo, onde o comando será aplicado.</li>
    <li>WHERE - Cláusula condicional, o resultado do comando está consicionado à que a cláusula seja satisfeita.</li>
    <li>GROUP BY - Cláusula de agrupamento de registros por uma ou mais colunas determinadas.</li>
    <li>HAVING - Cláusula condicional executada sobre cada agrupamento.</li>
    <li>ORDER BY - Cláusula de ordenação, retorna os registros ordenados conforme a/s coluna/s desejada/s .</li>
    <li>DISTINCT - Cláusula que consdiciona o resultado a não repetidos conforme uma coluna definida.</li>
</ul>

<strong>Operadores relacionais</strong>

<table style="height: 278px" border="1" width="431" cellspacing="0" cellpadding="0">
<tbody>
<tr>
<td valign="top" width="83"><strong>Operador</strong></td>
<td valign="top" width="142"><strong>Descrição</strong></td>
</tr>
<tr>
<td valign="top" width="83">&lt;</td>
<td valign="top" width="142">Menor que</td>
</tr>
<tr>
<td valign="top" width="83">&gt;</td>
<td valign="top" width="142">Maior que</td>
</tr>
<tr>
<td valign="top" width="83">&lt;=</td>
<td valign="top" width="142">Menor ou igual que</td>
</tr>
<tr>
<td valign="top" width="83">&gt;=</td>
<td valign="top" width="142">Maior ou igual que</td>
</tr>
<tr>
<td valign="top" width="83">=</td>
<td valign="top" width="142">Igual que</td>
</tr>
<tr>
<td valign="top" width="83">!=</td>
<td valign="top" width="142">Diferente que</td>
</tr>
<tr>
<td valign="top" width="83">BETWEEN</td>
<td valign="top" width="142">Entre de - O valor deve estar entre os valores especificados</td>
</tr>
<tr>
<td valign="top" width="83">LIKE</td>
<td valign="top" width="142">Como - É um operador de aproximação, utilizado nas buscas, seleciona os resultados que são aproximados com a expressão passada.</td>
</tr>
</tbody>
</table>

<strong>Funções de agregação</strong>

<ul>
    <li>AVG - Calcula a média de valores de uma coluna especificada.</li>
    <li>MAX - Retorna o maior valor dentro de uma coluna especificada.</li>
    <li>MIN - Retorna o menor valor dentro de uma coluna especificada.</li>
    <li>COUNT - Retorna o número de registros da seleção.</li>
    <li>SUM - Retorna a soma de todos os valores de uma determinada coluna.</li>
</ul>

É isso, espero que tenham gostado das definições, qualquer coisa entre em contato.  

Abraço  