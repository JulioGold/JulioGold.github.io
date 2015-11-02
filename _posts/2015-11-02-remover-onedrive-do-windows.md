---
layout: post
comments: false
title: "Remover OneDrive do windows"
excerpt: "Este aplicativo fica disponível no windows e mesmo desativando sua utilização pelas configurações do sistema ele continua na bandeja do sistema e nas opções do explorer."
date: 2015-11-02 17:17:00
mathjax: true
published: true
---

# Remover OneDrive do windows  

---
  
Este aplicativo fica disponível no windows e mesmo desativando sua utilização pelas configurações do sistema ele continua na bandeja do sistema e nas opções do explorer.  
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/assets/images/2015-11-02-remover-onedrive-do-windows/1.png)
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/assets/images/2015-11-02-remover-onedrive-do-windows/1-2.png)

Para remover de vez inclusive destes locais, basta seguir os seguintes passos:  

Abra o editor do registro do windows.  

Agora navegue até a seguinte chave: **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\Skydrive**
caso não exista a chave **Skydrive** você deve criá-la.
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/assets/images/2015-11-02-remover-onedrive-do-windows/3.png)  

Agora dentro da chave **Skydrive** você deve criar uma chave **REG_DWORD** com o nome **DisableFileSync**  
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/assets/images/2015-11-02-remover-onedrive-do-windows/4.png)

Configure o valor da chave conforme desejar, sendo:  
1 = OneDrive desativado (Sem o aplicativo chato no canto da barra e sem a opção no explorer, blz é isso que queremos!)  
0 = OneDrive ativado (Tudo volta ao normal.)  

![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/assets/images/2015-11-02-remover-onedrive-do-windows/5.png)
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/assets/images/2015-11-02-remover-onedrive-do-windows/6.png)
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/assets/images/2015-11-02-remover-onedrive-do-windows/7.png)

Pronto feito isso, salve e feche o editor do registro, esta mudança deve ter efeito imediato, porém se desejar ativar novamente, terá de reiniciar
o sistema.  

Sem o aplicativo chato no canto da barra:
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/assets/images/2015-11-02-remover-onedrive-do-windows/8.png)

Sem a opção no explorer:
![](https://raw.githubusercontent.com/JulioGold/JulioGold.github.io/master/assets/images/2015-11-02-remover-onedrive-do-windows/9.png)

Obrigado  
