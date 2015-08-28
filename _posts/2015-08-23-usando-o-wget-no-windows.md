---
layout: post
comments: false
title: "Usando o wget no windows"
excerpt: "Estava tentando baixar o Visual Studio 2015 do DreamSpark, porém o download da imagem iso é de 3,8 gb..."
date: 2015-08-23 15:45:00
mathjax: true
published: true
---

# Como executar um arquivo de script no sql server sem abrí-lo no management studio  

---

## Usando o wget no windows  

### O problema  
Estava tentando baixar o Visual Studio 2015 do DreamSpark, porém o download da imagem iso é de 3,8 gb, até então tudo bem, porém aproximadamente nos 60% do download
simplesmente ocorria algum erro e o download não era concluído, o pior é que através do browser não há uma maneira de continuar o download, pois o link de dowload é modificado
a cada vez que é realizado então o browser não sabe que o download deveria ser continuado e não iniciado novamente.  
Já havia tentado realizar o download umas 4 vezes, tanto pelo firefox quanto pelo chrome e o mesmo problema ocorria.  

Bem a solução então foi utilizar o wget para realizar o download, a minha surpresa foi que aproximadamente nos 60% o problema também ocorreu, porém com o wget eu consegui
utilizar outro link de download (Conforme havia comentado o link é modificado a cada vez) mas apontando para o mesmo arquivo que havia ficado incompleto, ou seja, é o mesmo que 
continuar um download de um link diferente.  

Legal né.  

Quem é do linux já conhece o wget mas quem é do windows provavelmente não, o wget serve basicamente para baixar qualquer coisa da web.  

Vamos aos detalhes  

O que tive de fazer por primeiro foi achar o wget para windows, tive de baixar o próprio wget e suas dependências, utilizei como uma versão portable mesmo, sem instaladores...  

O que fiz então, basicamente foi baixar o wget e suas dependências e colocar tudo na mesma pasta, você também pode fazer isso, mas se desejar algo rápido e fácil, criei um 
repositório no github onde este trabalho ja está feito, bastando fazer clone do repositório e usar o wget no windows.  

O repositório é este: https://github.com/JulioGold/wget  

Pronto agora para iniciar o download executei o seguinte comando:  

```  
wget.exe -c "http://LinkMalucoDoVisualStudioQueMudaTodaHoraEDaErro" -O "C:\temp\vs\en_visual_studio_enterprise_2015_x86_x64_dvd_6850497.iso"  
```  

E deixei executando...  
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/_posts/images/2015-08-23-usando-o-wget-no-windows/19.png)  

E olhe, sem surpresa alguma, não é que nos 60% ocorreu um problema novamente!  
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/_posts/images/2015-08-23-usando-o-wget-no-windows/21.png)  

E o que fazer agora para continuar o download?  
Simplesmente iniciei o download pelo navegador para pegar o novo link e depois executei o mesmo comando no wget, alterando apenas o link de download, vejamos:  
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/_posts/images/2015-08-23-usando-o-wget-no-windows/22.png)  

E...  
Funcionou:  
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/_posts/images/2015-08-23-usando-o-wget-no-windows/23.png)  

O download continuou de onde havia parado, mas não vou contar com o sucesso antes do término do download e verificar se o arquivo está íntegro.  

Bem chegando no final, hora de verificar:  
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/_posts/images/2015-08-23-usando-o-wget-no-windows/26.png)  

Montando a imagem...  
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/_posts/images/2015-08-23-usando-o-wget-no-windows/28 - Copia.png)  

Imagem montada e funcionando:  
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/_posts/images/2015-08-23-usando-o-wget-no-windows/29 - Copia.png)  

Pronto, tudo resolvido.  

Obrigado  