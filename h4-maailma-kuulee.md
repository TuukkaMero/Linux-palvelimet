# H4 maailma kuulee

## x)

a)

**Pilvipalvelimen vuokraus ja asennus**

- Hyödynnettiin GitHub Student Developer Packia

- Palvelin vuokrattiin DigitalOceanilta, domain Namecheapiltä

- Valittiin Debian 11 x64 ja edullisin 5 $ / kk droplet

- Datakeskukseksi valittiin Amsterdam (EU, GDPR)

- Domain susannalehto.me ohjattiin palvelimen IP-osoitteeseen DNS A -tietueilla



d)

**Palvelin suojaan palomuurilla**

- SSH-yhteys palvelimeen root-käyttäjällä

- Päivitystiedot haettiin apt-get update

- Asennettiin palomuuri UFW


e)

**Kotisivut palvelimelle**

- Luotiin uusi käyttäjä ja lisättiin sudo-oikeudet

- Root-käyttäjä lukittiin turvallisuuden parantamiseksi

- Asennettiin Apache-webbipalvelin

- Sallittiin HTTP-portti 80 palomuurissa

- Korvattiin Apachen testisivu omalla sisällöllä

- Otettiin userdir käyttöön ja luotiin käyttäjälle kotisivut public_html-hakemistoon


f)

**Palvelimen ohjelmien päivitys**

- Haettiin päivitystiedot

- Asennettiin normaalit päivitykset

- Asennettiin myös tietoturva- ja jakelupäivitykset

- Sallittiin SSH-portti 22

- Palomuuri otettiin käyttöön




**First Steps on a New Virtual Private Server – an Example on DigitalOcean and Ubuntu 16.04 LTS**

- GitHub Education -paketilla opiskelija saa VPS-palvelimen ja .me-domainin

- Virtuaalipalvelin luodaan DigitalOceanissa (Ubuntu)

- Kirjaudutaan root-käyttäjällä vain kerran ja vaihdetaan salasana

- Palomuuri otetaan käyttöön ja SSH sallitaan ensin

- Luodaan henkilökohtainen sudo-käyttäjä

- Root-käyttäjä lukitaan ja root-kirjautuminen estetään SSH:llä

- Ohjelmistot päivitetään heti haavoittuvuuksien estämiseksi

- Domain-nimi lisätään DNS A -tietueella osoittamaan palvelimen IP:hen

- Julkisia palveluja varten avataan tarvittavat portit (esim. 80/tcp)




## a)

Valitsin virtuaalipalvelimeni UpCloudilta

Kirjautumisen yhteyedessä sain ilmaisia kredittejä jotka käytin uuteen palvelimeen 

Normaalisti palvelimen hinta olisi n. 3e kuussa

Tässä luomani virtuaalipalvelin ja sen speksit:

![palvelin](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/palvelin.png)



## b)

Tässä tehtävässä tein alkutoimet palvelimelleni (tulimuuri, root tunnus kiinni ja ohjelmien päivitys)

Aloitin yhdistämällä pelvelimeen seuraavalla komennolla:

    ssh root@94.237.36.234

Aloitin tekemällä reijän palomuuriin ssh-yhteyttä varten ja kytkin palomuurin päälle

![tulimuuri](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/tulimuuri.png)

Seuraavaksi tein käyttäjän ja tästä käyttäjästä pääkäyttäjän

![upk](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/uusip%C3%A4%C3%A4k%C3%A4ytt%C3%A4j%C3%A4.png)

Kirjautuminen ilman roottia toimii:

![ilmanroot](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/tuukkakirjautuminen.png)

Lukitsin juuren käyttäjän komennolla:

    sudo usermod –lock root

Viimeiseksi päivitin palvelimen ohjelmat komennolla:

    sudo apt-get update

    sudo apt-get upgrade


## c)

Tässä tehtävässä asensin weppipalvelvelimen virtuaalipalvelimelleni

Aloitin asentamalla apache2 virtuaalipalvelimelleni

    sudo apt-get update
    sudo apt install apache2

Kokeilin apache asennuksen jälkeen, että testisivu tuli näkyviin

![testi](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/tuukanservu%20testisivu.png)

Seuraavaksi korvasin testisivun ja kokeilin sen toimivuutta

![korvaus](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/uusi%20index.png)

![testi](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/virtuaalipalvelin%20testisivu.png)

Tässä testisivu kokeiltuna myös puhelimella

![puhelin](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/testisivu%20puhelin.png)

Molemmat testit toimivat joten testisivu oli korvattu ja toimi kuten pitikin



## Lähteet 

https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/

https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/
