# T06: Accés remot - Escriptori remot (RDP)  

Per a fer aquesta pràctica haurem de tenir dues VM Windows i Zorin, les dues amb xarxa NAT per a que puguin veures entre elles dins la xarxa.
Farem comprovacions inicials amb ping entre elles.

![capt1](img/1.png)

![capt2](img/2.png)

Primer de tot, haurem de tenir una màquina virtual amb Windows i activar l’escriptori remot en aquesta. Des de configuració → Sistema → Escritorio remoto

![capt3](img/3.png)

Ara, afagerim un usuari d'escriptori remot

![capt4](img/4.png)

![capt5](img/14.png)

![capt6](img/15.png)

![capt7](img/16.png)

![capt8](img/17.png)

![capt9](img/18.png)

![capt10](img/19.png)

Seguidament, haurem d’entrar a la segona VM, una màquina amb Zorin. Provarem de conectarnos al escriptori remot de Windows per fer-ho hem d’obrir Remmina.

![capt11](img/5.png)

![capt12](img/6.png)

![capt13](img/7.png)

Ara activarem el control remot a Zorin, per fer-ho accedim a "Settings" → Share → On "Share Screen" seguidament activem "Remot Desktop" → Set Password.

![capt14](img/8.png)

![capt15](img/9.png)

Tot seguit, des de Windows ara podem conectarnos a zorin, amb Escritorio Remoto. Obrirem l’aplicació i introduïrem les dades d’acces. Les dades que haurem d'introduir, són les següents:
Equipo: usuari-VirtualBox.local 
Usuario: usuari

![capt16](img/10.png)

Aquí, haurem d'introduir la contrasenya que esta abaix de tot on ens surtia a la captura anterior

![capt17](img/11.png)

Un cop ens surti la seguent pestanya, haurem de clickar a "Sí" i ja estrem conectats de forma remotamanent

![capt18](img/12.png)

![capt19](img/13.png)

