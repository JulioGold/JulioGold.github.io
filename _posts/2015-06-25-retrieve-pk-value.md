---
layout: post
comments: false
title:  "Retrieve primary key value after inserted when pk is a uniqueidentifier"
excerpt: "Who was tried knows @@IDENTITY and SCOPE_IDENTITY() will not work at a uniqueidentifier type field, because the Id field isn't identity."
date:   2015-06-25 20:57:00
mathjax: true
published:   true
---

# Retrieve primary key value after inserted when pk is a uniqueidentifier

---

## Who was tried knows @@IDENTITY and SCOPE_IDENTITY() will not work at a uniqueidentifier type field, because the Id field isn't identity.

---

### Table with Id not identity but is a uniqueidentifier
```sql
    CREATE TABLE Contact (
        Id uniqueidentifier NOT NULL DEFAULT NEWID(),
        Name nvarchar(255),
        Email nvarchar(255),
        CONSTRAINT [PK.Contact] PRIMARY KEY (Id)
    );
```

### It's not work. @@IDENTITY variable not contain the inserted value of pk
```sql    
    INSERT INTO Contact(Name,Email)
    VALUES('Ana','ana@email.com')
    SELECT @@IDENTITY;
```

### It's not work. SCOPE_IDENTITY() function can't get the inserted value of pk
```sql
    INSERT INTO Contact(Name,Email)
    VALUES('Bruna','bruna@email.com')
    SELECT SCOPE_IDENTITY();
```

### It's work. The output parameter will return the inserted value of pk
```sql
    INSERT INTO Contact(Name,Email)
    OUTPUT INSERTED.Id
    VALUES('Caroline','caroline@email.com');
```

### It's work. Another way to get value of inserted pk
```sql
    DECLARE @identifier AS TABLE( Id uniqueidentifier);
    INSERT INTO Contact(Name,Email)
    OUTPUT INSERTED.Id INTO @identifier
    VALUES('Daiana','daiana@email.com');
    SELECT Id FROM @identifier;
```
