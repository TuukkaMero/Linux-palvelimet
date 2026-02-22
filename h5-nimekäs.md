# H5 Nimekäs

## a)

Aloitin ostamalla julkisen nimen joka on tässä tapauksessa **tuukkamero.com**

![domain](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/domain%20list.png)

Seuraavaksi laitoin nimen osoittamaan omaan koneeseeni

Lisäsin NameCheapin kautta A-recordin

![arecord](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/a-record.png)

Kokeilin että domain toimii kuten pitääkin 

![curl](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/tuukkamero.com%20curl.png)

Tässä sivu myös selaimessa

![tuukkacom](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/tuukkamero.com.png)




## b)

Tässä teshtävässä tein kaksi alidomainia

![alidomain](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/alidomainit.png)

Tässä kokeilin että ne toimivat

![www](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/www..png)

![testi](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/testi..png)




## c)

Tutkin tuukkamero.com DNS-tietoja ensin **host** komenolla joka tulosti seuravaa:

![host](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/host%20komento.png)

host komento on yksinkertainen DNS-tarkistustyökalu

Perustulostus näyttää vain kysytyn tyyppiset tietueet, esim. A- tai MX-tietueet.



Seuraavaksi kokeilin samalle nimelle **dig** komentoa

![dig](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/dig%20komento.png)

dig on paljon kattavampi työkalu kuin host

Näyttää koko vastauksen, mm. kyselyn ID:n, aikaleiman, käyttöönottoparametrit

Voit kysyä eri tietueita: A, AAAA, MX, NS, TXT, SOA



NameCheap.com hallintapaneelista näkyi:

DNS:ssä näkyy samat A-, AAAA-, MX- ja NS-tietueet

Dig ja host kertovat myös TTL:n ja nimipalvelimen, mikä hallintapaneelissa on usein vain oletusarvo


Seuraavaksi ajoin samat komennot mutta vaihdoin tuukkamero.com tilalle **terokarvinen.com**

![host](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/host%20terokarvinen.png)

- A-tietue: 139.162.131.217 → web-palvelimen IP

- MX-tietue: mx.runbox.com prioriteetti 10 → sähköpostipalvelin

![dig](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/dig%20terokarvinen.png)

- QUESTION SECTION

Kysely: haetaan A-tietuetta domainille.

- ANSWER SECTION

Vastaus nimipalvelimelta: IP 139.162.131.217. TTL = 10800 s

- Query time

Kuinka kauan kysely kesti

- SERVER

DNS-palvelin, joka vastasi kyselyyn (tässä Googlen 8.8.8.8)




Viimeisenä kokeilin Google.com

![host](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/host%20google.png)

- A-tietue: 142.251.38.78 → yksi Googlen IPv4-osoitteista

- AAAA-tietue: 2a00:1450:4026:803::200e → IPv6-osoite

- MX-tietue: smtp.google.com prioriteetti 10 → sähköpostipalvelin

![dig](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/dig%20google.png)

- QUESTION SECTION

Kysely: haetaan A-tietuetta domainille

- NSWER SECTION

Nimipalvelimen vastaus: IP = 216.58.209.174. TTL = 74 s

- Query time

Kuinka nopeasti kysely valmistui

- SERVER

DNS-palvelin, joka vastasi kyselyyn (tässä 8.8.8.8)



## Lähteet 

https://terokarvinen.com/linux-palvelimet/
