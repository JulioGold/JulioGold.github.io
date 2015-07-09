---
layout: post
comments: false
title: "Pegar apenas a última parte de uma string"
excerpt: "Com este script conseguimos pegar apenas a última parte de uma string"
date: 2012-12-10 07:58:00
mathjax: true
published: true
---

# Pegar apenas a última parte de uma string

---

Com este script conseguimos pegar apenas a última parte de uma string, por exemplo em um nome de uma pessoa, será retornado o sobrenome da mesma.  

```sql
DECLARE @texto AS varchar(200)

SET @texto = 'Um texto qualquer'

--SET @texto = 'Texto'

SELECT CASE WHEN CHARINDEX(' ', REVERSE(RTRIM(LTRIM(@texto)))) < 1 THEN @texto ELSE LTRIM(RTRIM(RIGHT(LTRIM(RTRIM(@texto)), CHARINDEX(' ', REVERSE(RTRIM(LTRIM(@texto))))))) END
```

abraço  

Referências:  
[REVERSE (Transact-SQL)](http://msdn.microsoft.com/pt-br/library/ms180040.aspx)  
[CHARINDEX (Transact-SQL)](http://msdn.microsoft.com/pt-br/library/ms186323.aspx)  