# H3 Hello Web Server

## x)

## Name based virtual host support

- IP-based: jokaisella sivustolla oma IP-osoite

- Name-based: useita sivustoja samassa IP:ssä, erotellaan Host-headerin avulla

- Name-based on suositeltu (helpompi, säästää IP-osoitteita)

  Name based virtual hostin käyttö:

  - Jokaisella sivustolla oma VirtualHost-lohko
 
  - Pakolliset: DocumentRoot ja ServerName
 
  - Ensimmäinen VirtualHost = default vhost
 

  ## Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address

  - Yksi IP-osoite → useita verkkotunnuksia
 
  - Apache erottaa sivustot Host-headerin perusteella
 
  - Esim: terokarvinen.com, botbook.com → sama IP
 
    Perusvaiheet:
    
1. Asenna Apache

2. Korvaa oletussivu

3. Lisää uusi VirtualHost

4. Ota sivusto käyttöön

5. Käynnistä Apache uudelleen

6. Testaa



## a)

Apache oli jo minulla asennettuna joten testasin suoraan vastaako se localhost osoitteesta

![localhost](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/localhost%20default.png)

Palvelin vastasi localhost osoitteesta joten kaikki toimii suunnitellusti


## b)

Aloitin avaamalla lokin, josta löytäisin rivit jotka syntyvät, kun lataan palvelimeltani uuden sivun:

    sudo tail /var/log/apache2/access.log

Lokista paljastui seuraavat rivit:

![loki](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/loki.png)

Yksittäiseltä riviltä löytyy seuraavat tiedot:

1. asiakkaan IP osoite - **127.0.0.1**

2. Identd-käyttäjä - **Tässä tapauksessa ei käytössä joten -**

3. Autentikoitu HTTP-käyttäjä - **Tässä tapauksessa ei kirjautumista joten -**

4. Aikaleima - **[27/Jan/2026:14:46:44 +0200]**

5. HTTP-pyyntö - **GET / HTTP/1.1**

6. HTTP-tilakoodi - **200**

7. Vastauksen koko tavuina - **3380**

8. Referer - **Käyttäjä kirjoitti osoitteen suoraan joten -**

9. User-Agent - **Mozilla/5.0 (X11; Linux x86_64; rv:140.0) Gecko/20100101 Firefox/140.0"**

   - Kertoo selaimen, käyttöjärjestelän ja selainmoottorin
  


## c) 

Aloitin asettamalla default palvelimen pois päältä seuraavalla tavalla:

![a2dissite](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/a2dissite.png)

Seuraavaksi loin uuden name based virtual hostin jonka nimeksi asetin **tuukka.conf**

![tuukkaconf](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/tuukka.conf.png)

Asetin palvelimen päälle samalla tavalla kuin asetin edellisen pois, mutta **a2dissite** tillalle laitoin **a2ensite**

![a2ensite](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/a2ensite.png)

tuukka.conf sisältö:

![sisältö](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/tuukka.conf%20sis%C3%A4lt%C3%B6.png)

Sivun sisältö:

![sivu](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/tuukka.conf%20sivu.png)

Tässä sivu palvelimen etusivulla:

![etusivu](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/example.com.png)



## e)

Käytin validin HTML5 sivun luomiseen aikaisemmin luomaani tuukka.conf palvelinta

Tässä luomani sivun sisältö:

![validisivu](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/validisivu.png)

Latasin sivun tiedoston **W3C Markup Validation Serviceen**

![w3c](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/w3c.png)

Virheitä ei löytynyt joten sivu on validi ja testi onnistui


## f)

Tässä esimerkit curl ja curl -l komennoista:

**Curl**

![curl](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/curl.png)

**curl -l**

![curl-l](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/curl%20-l.png)

Curl komento lataa koko sivun sisällön ja tulostaa sen terminaaliin

Curl -l komento tulostaa HTTP-response headers, eikä mitään html sisältöä



## Lähteet 

https://httpd.apache.org/docs/2.4/vhosts/name-based.html

https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/
