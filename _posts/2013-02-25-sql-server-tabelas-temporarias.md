---
layout: post
comments: false
title: "SQL Server tabelas temporárias"
excerpt: "Por muitas vezes precisamos utilizar tabelas temporárias, segue abaixo scripts sobre um pouco do funcionamento das mesmas."
date: 2013-02-25 20:10:00
mathjax: true
published: true
---

# SQL Server tabelas temporárias

---

Por muitas vezes precisamos utilizar tabelas temporárias, segue abaixo scripts sobre um pouco do funcionamento das mesmas.  

Primeiramente uma temporária que pode ser "vista" de todas as seções.
Sua principal característica são os dois ## que indicam a visão pelas demais seções.  

```sql
------------------------------------------------------------------------------------------
IF OBJECT_ID('tempdb.dbo.##TabelaTmp') IS NOT NULL DROP TABLE ##TabelaTmp /*Se o objeto ja existir, exclui o mesmo.*/
SELECT Valor
INTO ##TabelaTmp /*Esta tabela está disponível para todas as seções. Cria a tabela temporária automaticamente.*/
FROM
(
	/*Lista gerada manualmente.*/
	SELECT 1 AS Valor
	UNION
	SELECT 2 AS Valor
	UNION
	SELECT 3 AS Valor
	UNION
	SELECT 4 AS Valor
	UNION
	SELECT 5 AS Valor
) AS T /*É necessário definir um alias para a seleção.*/
------------------------------------------------------------------------------------------
```

Agora uma temporária que pode ser "vista" apenas na seção atual.
Sua principal característica é o único # que indica a visão apenas pela seção atual.

```sql
------------------------------------------------------------------------------------------
IF OBJECT_ID('tempdb.dbo.#TabelaTmp') IS NOT NULL DROP TABLE #TabelaTmp /*Se o objeto ja existir, exclui o mesmo.*/
SELECT Valor
INTO #TabelaTmp /*Esta tabela está diponível apenas nesta seção. Cria a tabela temporária automaticamente.*/
FROM
(
	/*Lista gerada manualmente.*/
	SELECT 1 AS Valor
	UNION
	SELECT 2 AS Valor
	UNION
	SELECT 3 AS Valor
	UNION
	SELECT 4 AS Valor
	UNION
	SELECT 5 AS Valor
) AS T /*É necessário definir um alias para a seleção.*/
------------------------------------------------------------------------------------------
```

A tabela em variável deve ter sua estrutura previamente declarada estará disponível apenas no momento da execução da query.

```sql
------------------------------------------------------------------------------------------
DECLARE @TabelaVar AS table( Valor integer ) /*É necessário declarar uma tabela variável, esta tabela fica apenas na memória e é visível apenas na mesma query.*/
INSERT INTO @TabelaVar
/*Lista gerada manualmente.*/
SELECT 1 AS Valor
UNION
SELECT 2 AS Valor
UNION
SELECT 3 AS Valor
UNION
SELECT 4 AS Valor
UNION
SELECT 5 AS Valor
SELECT * FROM @TabelaVar
------------------------------------------------------------------------------------------
```

Obrigado

Referências:  
[Variáveis tipo table vs tabelas temporárias sql server](http://www.dotnetbr.com/2011/05/24/variaveis-tipo-table-vs-tabelas-temporarias-sql-server/)  
[Tabelas Temporárias](http://www.sqlmagazine.com.br/colunistas/PauloRibeiro/20_Tabelas.asp)  
[DECLARE @local_variable (Transact-SQL)](http://msdn.microsoft.com/en-us/library/ms188927.aspx)  
[Variáveis Table no SQL Server 2000](http://www.devmedia.com.br/variaveis-table-no-sql-server-2000/4587)  