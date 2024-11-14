## x) Tiivistelmä
- Wiresharkin oppaat
- Monikäyttöinen työkalu ip pakettiliikenteen tarkkasteluun
- Wiresharkin analysointityökalut
- Suodattimet ja hakutyökalut

- Ffuf = nopea työkalu joka voi löytää piilotetut hakemistot.
- Wordlist tarvitaan
- Wordlist pitää yhdistää kohteeseen
- Suodattimien käyttöllä voidaan helpottaa palautettujen tietojen(polut ja http-koodit) tarkastelua


## a) Hyökkäyksen demonstrointi

a)	Ensiksi valitsin hyökkäyksen. Koin omaan osaamistasoon sopivaksi tunnilla käydyn vsftpd. Löysin kuitenkin netistä selkeät ohjeet myös toiseen hyökkäykseen, jota halusin kokeilla.
Testasin että koneet saavat yhteyden toisiin, mutteivat nettiin. 
![ping8.8.8.8 ja meta_kali](https://github.com/JohannaLap/H3/blob/main/ping8.8.8.8%20ja%20meta_kali.png)

![ping 8.8.8.8 ja kali_meta](https://github.com/JohannaLap/H3/blob/main/ping8.8.8.8%20ja%20kali_meta.png)

Aloitin komennolla ‘search vsftpd’. Tällä katsotaan mahdolliset exploitit.

![vsftpd](https://github.com/JohannaLap/H3/blob/main/vsftpd.png)

Valitsin 1 moduulin.

![use 1](https://github.com/JohannaLap/H3/blob/main/use%201.png)

Asetin ‘RHOST’ metasploitable koneen. 

![set rhost](https://github.com/JohannaLap/H3/blob/main/set%20rhost.png)

Tarkistin, että portti ja r host on oikein. 

![show options](https://github.com/JohannaLap/H3/blob/main/show%20options.png)

Ajoin komennot.

![exploit ja run](https://github.com/JohannaLap/H3/blob/main/exploit%20ja%20run.png)

Tässä vielä kokeilu SAMBAsta
![SAMBA](https://github.com/JohannaLap/H3/blob/main/SAMBA%20.png)


## b) Lähdekoodi

Tämän jälkeen 'edit' komennolla pääsin tarkastelemaan lähde koodia. Lähde koodin tulkitsemisen koin melko haasteellisena. Toki seiltä on helposti löydettävissä kohdat joista nähdään mikä viesti tulostetaan näytölle, jos jotakin menee pieleen.
Exploit tarkoittanee yhteyden muodostusta. 
Myös kommentti #Do not bother reading the response from password, just try the backdoor, viitannee siihen ettei salasanan tarkistusta tarvita.

![editkomento](https://github.com/JohannaLap/H3/blob/main/edit%20komento%20.png)

![editkomento2](https://github.com/JohannaLap/H3/blob/main/edit%20komento2.png)

Otin myös lähdekoodit SAMBAsta

![kuvateksti](https://github.com/JohannaLap/H3/blob/main/SAMBA%20sourcecode.png)
![kuvateksti](https://github.com/JohannaLap/H3/blob/main/SAMBA%20sourcecode2.png)

## c) Snif snif
Wiresharkilla pystyy filtteriä käyttämällä valitsemaan mitä liikennettä seuraa. Voi valita esim tcp tai tietyn osoitteen, jonka liikennettä seuraa. Sitä ei tosin pysty määrittelemään onko kyseinen osoite source vai destination. 
Myös portin asettaminen filtteriksi onnistuu, jolloin on helppo seurata tietyyn porttiin tapahtuvaa liikennettä. 


## d)

## e)

## Lähteet
Karvinen, 2023: Find Hidden Web Directories - Fuzz URLs with ffuf  https://terokarvinen.com/2023/fuzz-urls-find-hidden-directories/
Popov 2024: Hacktricks: Wireshark tricks  https://book.hacktricks.xyz/generic-methodologies-and-resources/basic-forensic-methodology/pcap-inspection/wireshark-tricks#improve-your-wireshark-skills
https://blog.securelayer7.net/attacking-metasploitable-2-using-metasploit/
https://www.youtube.com/watch?v=v8ThuHceRfM
https://westoahu.hawaii.edu/cyber/forensics-weekly-executive-summmaries/8424-2/










