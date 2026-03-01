# h6 Salataanpa

## x)

**Lets encrypt 2024: How it works**

- Let’s Encrypt ja ACME mahdollistavat HTTPS-sertifikaattien hankkimisen ja uusimisen automaattisesti web-palvelimelta ilman manuaalista työtä

- Kun domainin hallinta on vahvistettu useista verkon näkökulmista, asiakas saa oikeuden hallita kyseisen domainin sertifikaatteja

- Sertifikaatin hankinta tehdään lähettämällä CSR-pyyntö (Certificate Signing Request), joka allekirjoitetaan sekä palvelimen avaimella että ACME-tilin avaimella

- CA tarkistaa allekirjoitukset ja myöntää sertifikaatin sekä julkaisee sen Certificate Transparency -lokeihin


**Basic configuration example**

- Apache HTTP Server SSL-peruskonfiguraatio: lataa mod_ssl, kuuntele porttia 443 ja määritä VirtualHost, sertifikaatti ja avain

- Vahva salaus: rajoita käytettävät cipherit (SSLCipherSuite) ja tarvittaessa pakota vahvempi salaus tietyille URL-alueille

- OCSP Stapling: palvelin tarkistaa ja välittää sertifikaatin peruutustilan asiakkaille, mikä parantaa suorituskykyä ja yksityisyyttä

- Asiakasvarmennus: voidaan vaatia käyttäjiltä sertifikaatti koko sivustolle tai vain tiettyyn hakemistoon




## a)

Tässä tehtävässä hankin palvelimelleni ilmaisen TLS-sertifikaatin Let's Encryptiltä

Aloitin asentamalla **certbotin komennoilla:

    sudo apt update 

    sudo apt install certbot python3-certbot-apache

Seuraavaksi hankin sertifikaatin domainille ajamalla seuraavan komennon 

![sertifikaatti](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/sertifikaatti.png)

Sertifikaatin hankkimisen jälkeen törmäsin ongelmaan jossa sivuni ei näkynyt enää selaimessa 

Kokeilin komentoa 

    sudo ufw status

Sieltä homasin että portti 443 ei näy 

Korjasin ongelman komennolla 

    sudo ufw allow 443/tcp

    sudo ufw reload

Lopputulos näytti tältä ja ongelmani oli korjattu 

![443](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/443.png)

Lukon kuva oli myös ilmestynyt selaimeen joten serifikaattini oli toiminnassa

![lukko](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/lukko.png)




## b)

Tässä tehtävässä testasin sivuni TLS laadunvarmennustyökalulla joka oli tässä tapaukessa **SSL labs**

![a](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/a%20sertifikaatti.png)

testi näytti siltä kuin pitikin


## Lähteet 

https://letsencrypt.org/how-it-works/

https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample

https://terokarvinen.com/linux-palvelimet/#h7-maalisuora



