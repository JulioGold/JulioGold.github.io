---
layout: post
comments: false
title: "Unir tabelas tipo merge"
excerpt: "Unir tabelas como uma espécie de merge entre tais"
date: 2015-07-08 22:04:00
mathjax: true
published: true
---

# Unir tabelas tipo merge

---

Unir tabelas como uma espécie de merge entre tais, deixando determinada tabela prevalecer sobre outra:  

```sql

DECLARE @T1 AS TABLE(id int,value varchar(3));
DECLARE @T2 AS TABLE(id int,value varchar(3));
DECLARE @T3 AS TABLE(id int,value varchar(3));

INSERT INTO @T1
SELECT 1,'A'
UNION
SELECT 2,'Y'
UNION
SELECT 3,'C'
UNION
SELECT 4,'C'
UNION
SELECT 5,'X'

INSERT INTO @T2
SELECT 2,'B'
UNION
SELECT 5,'E'
UNION
SELECT 4,'D'

-- O que tem apenas em T1 e não tem em T2.
INSERT INTO @T3 SELECT T1.id, T1.value FROM @T1 AS T1 WHERE T1.id NOT IN (SELECT id FROM @T2);

-- Tudo da lista que deve prevalecer (T2) mais o que não tem nesta lista (T3).
SELECT id,value FROM @T2 UNION SELECT id,value FROM @T3;

```

Obrigado  