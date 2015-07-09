---
layout: post
comments: false
title: "Como executar um arquivo de script no sql server sem abrí-lo no management studio"
excerpt: "Quando necessitar executar um script muito grande na base de dados..."
date: 2015-07-6 20:48:00
mathjax: true
published: true
---

# Como executar um arquivo de script no sql server sem abrí-lo no management studio

---

Quando necessitar executar um script muito grande na base de dados você pode executar o arquivo sem abrí-lo no management studio.  
Isto também é interessante para preservar o encoding do arquivo, pois dependendo o encoding pode ficar totalmente errado.

No prompt execute o seguinte comando:

```
sqlcmd -S SERVER\INSTANCE -d DATABASE -U USERNAME -P PASSWORD -i C:\temp\Script.sql -o C:\temp\Output.txt
```

O parâmetro **-o C:\temp\Output.txt** serve apenas para que não fique jogando os resultados das execuções no console,  
pois isto faz com que demore mais para terminar  a execução.
Ter atenção pois com o parâmetro **-d DATABASE** estamos indicando a base que desejarmos executar o script, porém se  
dentro do script existir algum comando **USE DATABASE** a base de dados será alterada e o parâmetro pode ter servido para nada.

Obrigado

Referências:

[SQL Server - Running large script files](http://stackoverflow.com/questions/222442/sql-server-running-large-script-files)  
[Big SQL Script File Runner](http://bigsqlrunner.codeplex.com/)