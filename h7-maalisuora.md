# h7 Maalisuora

## a)

Tässä tehtävässä kirjoitin ja ajoin "hei maailma kolmella eri kielellä

Ensimmäiseksi **python**:

Loin tiedoston konennolla 

   nano hei.py

Tiedoston sisältö:

![hei](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/hei.py.png)

Ajo:

![pyajo](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/hei.py%20ajo.png)



Toiseksi **bash**:

Loin tiedoston komennolla

    nano hei.sh

Tiedoston sisältö:

![heish](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/hei.sh.png)

Ajo:

![shajo](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/hei.sh%20ajo.png)



Kolmanneksi **C**:

Loin tiedoston komennolla

    nano hei.c

Tiedoston sisältö:

![heic](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/hei.c.png)

Ajo:

![cajo](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/hei.c%20ajo.png)




## c)

Tässä tehtävässä laitoin LInuxiin uuden komennon, niin että kaikki voivat ajaa sitä

Komennon tiedoston sisältö:

![komento](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/oma%20komento.png)

Tein siitä suoritettavan seuraavalla komennolla:

   sudo chmod +x /usr/local/bin/tervehdi

Komento tulostaa:

![tervehdi](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/tervehdi.png)




## d)

Tässä tehtävässä ratakaisin seuraavan vanhan laboratorioharjoituksen:

https://terokarvinen.com/2018/arvioitava-laboratorioharjoitus-linux-palvelimet-ict4tn021-6-torstai-alkukevat-2018-5-op/?fromSearch=arvioitava

Aloitin asentamalla LAMP:

    sudo apt install apache2 mariadb-server php libapache2-mod-php php-mysql

Seuraavaksi käynnistin palvelimen:

    sudo systemctl restart apache2

Seuraavaksi testasin php suraavalla tavalla:

    sudo nano /var/www/html/info.php

![php](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/php.png)

![sivu](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/php%20sivu.png)

Keräsin koko hajoituksen ajan kuormaa komennolla **top**

Tallensin tiedot tieodstoon kuormitus.log

    vmstat 60 > kuormitus.log

Seuraavaksi loin sorkkacrm databasen käyttämällä **MariaDB** seuraavalla tavalla:

![sorkkacrm](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/sorkkacrm.png)

Seuraavaksi loin PHP ohjelman joka lukee asiakkaat:

    sudo mkdir /var/www/sorkkacrm

    sudo nano /var/www/sorkkacrm/index.php

![php](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/php%20ohjelma.png)

Seuraavat vaiheet:

![vaiheet](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/vaiheet.png)

sorkkacrm.conf sisältö:

![sisält](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/sorkkacrm.conf.png)

Simuloin DNS hosts tiedostolla:

    sudo nano /etc/hosts

    127.0.0.1 sorkkacrm.example.com


Tarkastelin epäonnistuneita ssh yrityksiä seuraavalla komennolla:

![failed](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/failed%20password.png)

Komento ei tulostanut mitään joten epäonnistuneita yrityksiä ei ollut

Seuraavaksi loin Sorkka ja Rauta OY:n sivun 

    sudo mkdir /var/www/rauta

    sudo nano /var/www/rauta/index.html

![sjr](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/sorkka%20ja%20rauta%20.png)

Lisäsin hosts tiedostoon 

    127.0.0.1 rauta.example.com

![sjrs](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/sorkka%20ja%20rauta%20selain.png)

Seuraavaksi tein Einarille käyttäjän

    sudo adduser einari

    sudo a2enmod userdir

    sudo systemctl restart apache2

Einarin kotisivun luonti:

    su - einari

    mkdir public_html

    nano public_html/index.php

![ephp](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/einari%20php.png)

![es](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/einari%20sivu.png)


Kuormitusanalyysi:

- CPU kuormitus oli matala (load average alle 0.50)

- RAM käyttö pysyi alle 30 %

- Apache ja MariaDB käyttivät suurimman osan resursseista



## Lähteet 

https://terokarvinen.com/2018/arvioitava-laboratorioharjoitus-linux-palvelimet-ict4tn021-6-torstai-alkukevat-2018-5-op/?fromSearch=arvioitava

https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/

https://terokarvinen.com/linux-palvelimet/#h7-maalisuora

https://terokarvinen.com/2007/12/04/shell-scripting-4/

https://www.w3schools.com/php/
