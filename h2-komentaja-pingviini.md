# H2 Komentaja Pingviini

## x)

Peruskomentoja:

pwd - Current working directory

cd - change directory

ls - list files in working directory

mkdir - make a new directory

mv - move or rename directory 

cp - copy 

rm - remove

history - history of commands you have ran


## a) 

Asensin micro editorin seuraavalla tavalla:

![microasennus](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/micro%20asennus.png)

Tarkistin että se on asennettu seuraavalla komennolla:

![microversio](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/micro%20versio.png)

Micro oli asennettu oikein enkä törmännyt ongelmiin 




## b)

Tässä tehtävässä asensin kolme uutta komentoriviohjelmaa. Ohjelmiksi valitsin **htop**, **ncdu** ja **cowsay**

Näin asensin kaikki kolme yhdellä apt-get komennolla:

![3asennusta](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/3%20asennusta.png)

**Htop - Prosessien hallinta**

![htop](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/htop.png)

**ncdu - levytilan analyysi**

![ncdu](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/ncdu.png)

**cowsay - tekstin tulostus**

![cowsay](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/cowsay.png)




## c)

Tässä tehtävässä esittelen muutaman tärkeän kansion ja niiden sisällön

**/ - root directory**

![root](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/root.png)

**/home/ - käyttäjien kotihakemistot**

![home](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/home.png)

**/home/tuukka/ - yksittäisen käyttäjän kotihakemisto**

![hometuukka](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/hometuukka.png)

**/etc/ - järjestelmän asetustiedostot**

![etc](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/etc.png)

**/media/ - irrotettavat laitteet**

![media](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/media.png)

**/var/log/ - Lokitiedostot**

![varlog](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/varlog.png)




## d) 

Tässä pari esimerkkiä grep komennon käytöstä:

**grep root /etc/passwd - Tulostaa kaikki rivit /etc/passwd-tiedostosta, joissa esiintyy sana root**

![greproot](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/greproot.png)

**grep -r bash /etc - Käy koko /etc-hakemiston läpi ja näyttää rivit, joissa esiintyy sana bash**

![grepbash](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/grepbash.png)



## e)

Tässä esimerkki putken käytöstä:

**ps aux | grep bash - Etsii prosessin aux ja näyttää vain rivit, joissa on bash**

![putki](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/putki.png)



## f)

Tässä tehtävässä listaan koneeni raudan **sudo lshw -short -sanitize** komennolla ja selitän listauksen 

![lshw](https://github.com/TuukkaMero/Linux-palvelimet/blob/main/lshw.png)

Tässä listauksessa näkyy kaikki käyttämäni koneen tiedot. Listaan perään jotain tärkeimmistä:

system - tässä tapauksessa ei fyysistä konetta joten tulosteeksi tuli vain virtualbox

memory - virtuaalikoneen käytettävissä oleva RAM 4GiB

processor - tässä tapauksessa prosessorina isäntäkoneen oma 12. sukupolven i5

disk - näyttää koneen 64gb virtuaalikiintolevyn


## Lähteet 

https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited

https://terokarvinen.com/linux-palvelimet/#h2-komentaja-pingviini








