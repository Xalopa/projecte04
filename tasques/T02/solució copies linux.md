# Part 2: Còpia seguretat servidor Linux

Com en el cas de la VM de Windows, haurem de tenir dos discs durs: un per defecte i un segon on emmagatzemarem les còpies.

![capt1](img2/1.png)

Quan entrem a la màquina, verifiquem que aquest disc sigui detectat.

![capt2](img2/2.png)

Generem una partició al nou disc amb la comanda

![capt3](img2/3.png)

Quan ens aparegui el 'menú', seguirem les instruccions:

n → Per crear una nova partició
p → Per indicar que és primària
Enter
Enter
Enter
W → Per guardar i sortir

![capt4](img2/4.png)

Formategem el disc en format XFS, però abans haurem d'instal·lar el servei XFS.

![capt5](img2/6.png)

![capt6](img2/7.png)

A continuació, crearem un directori i hi muntarem el disc corresponent.

![capt7](img2/8.png)

Seguidament, podem confirmar que s’ha muntat correctament fent servir la comanda corresponent.

![capt8](img2/9.png)

Tot seguit instal·larem duplicity, la utilitat que permet automatitzar les còpies de seguretat.

![capt9](img2/10.png)

Donarem d’alta dos usuaris nous i ens assegurarem que cadascun tingui la seva carpeta pròpia.

![capt10](img2/11.png)

![capt11](img2/12.png)

A continuació generarem quatre arxius de 10 MB a l’interior del directori creat prèviament.

![capt12](img2/13.png)

Per poder comprobar si ho hem fet bé, fem la seguent comanda:

![capt13](img2/14.png)

Realitzarem la còpia de seguretat amb duplicity; durant el procés ens sol·licitarà una frase de pas, que servirà per xifrar-la.

![capt14](img2/15.png)

Un cop finalitzat el procés, es pot comprovar el contingut que s’ha generat dins del directori de destinació.

![capt15](img2/16.png)













