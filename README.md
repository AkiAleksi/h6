# h6


# a.)

The OS pwns you. Asenna Windows virtuaalikoneeseen samaan verkkoon hyökkäyskoneen kanssa. Kokeile, että saat koneen irrotettua Internetistä.


Loin uuden virtuaalikoneen. Valitsin tyypin ja version(windows 10).


<img width="973" alt="okokokokok" src="https://github.com/AkiAleksi/h6/assets/112399816/6888f3ed-27bf-4096-9e6f-7cb58c0f8e2f">


Asetin muistin ja prosessorin. Laitoin myös tallenustilan seuraavasta ikkunasta.
Siitä ei kuitenkaan tullut otettua screenshottia.


<img width="968" alt="öööööö" src="https://github.com/AkiAleksi/h6/assets/112399816/ecbb0220-03c8-4a71-b5b3-f2bbfd08ef2b">



Avasin virtuaalikoneen.
Tein setupin.






<img width="537" alt="ggggggg" src="https://github.com/AkiAleksi/h6/assets/112399816/c42bceee-ad91-43c1-8dc3-edfede66e954">



Windows aukesi


<img width="512" alt="öäöäööääö" src="https://github.com/AkiAleksi/h6/assets/112399816/0f3c6775-3ff5-419c-940d-5bb0718ee5a6">


Muutin network kohdasta asetuksia, jotta hyökkääjän ja kohteen välille saadaan oma verkko.
Valitsin host-only network, jossa hyökkäävä kone on kiinni.




<img width="705" alt="plplplplplplpl" src="https://github.com/AkiAleksi/h6/assets/112399816/d7f6932e-9c14-4c8d-9570-2d7db3bad45e">


Windows kone on irroitettu netistä.



<img width="493" alt="loputulos" src="https://github.com/AkiAleksi/h6/assets/112399816/e19d0f9e-15fb-47f7-bc5a-9bd20d13aaae">


# b.)

Trustme.lnk. Kokeile PhishSticksin revshell vihamielistä tiedostoa, joka avaa käänteisen shellin hyökkääjän koneelle. Selitä, mitä tapahtuu ja miksi. Testaa, että pysyt antamaan kohdekoneelle komentoja reverse shellin kautta.

Laitoin ensiksi hyökkäyskoneelle Netcutin exen. Tein raport.txt tiedoston. Laitoin ne omaan kansioonsa.

<img width="718" alt="Screenshot 2023-12-01 at 19 53 23" src="https://github.com/AkiAleksi/h6/assets/112399816/e2c30517-c2dc-4916-91df-dbdc5b7dc0a8">

Latasin revshell-skripti kohdekoneelle. Määritin sille oikean ip-osoitteen ja portin. Reverse shelli ottaa yhteyttä siihen.

<img width="509" alt="Screenshot 2023-12-01 at 19 56 27" src="https://github.com/AkiAleksi/h6/assets/112399816/f1582b81-aa5d-4fca-ba10-3cf806584647">

Tein myös hello txt filen kansioon. Tiedostossa luki hello.

<img width="408" alt="Screenshot 2023-12-01 at 20 00 42" src="https://github.com/AkiAleksi/h6/assets/112399816/2d4d46ec-bf4b-4372-a814-2f5cd6460d18">

Komennolla python3 -m http.server 80 web-palvelin käynnistyy. Revshell-skripti lataa siitä tarvittavat asiat. komennolla nc -lvnp 9001 netcut menee päälle.

Kun ajetaan revshell-skripti kohdekoneelta se lataa nc64.exe ja raport.txt. Se käynnistää myös Netcut piilotetussa Powershell-ikkunassa. Se ottaa yhteyttä hyökkäyskoneelle. raport.txt -tiedosto aukeaa.

<img width="744" alt="Screenshot 2023-12-01 at 20 16 28" src="https://github.com/AkiAleksi/h6/assets/112399816/f7908527-e87b-40a2-bb26-d5cbe3bf073d">

revshell yhteys on auki. Avasin hello.txt tiedoston revshellin kautta.


<img width="1260" alt="Screenshot 2023-12-01 at 20 17 30" src="https://github.com/AkiAleksi/h6/assets/112399816/133103d6-20df-45b4-9ce4-ad221cda6b83">

# d.)
PageRank. Laita linkki raporttiisi kurssisivun kommentiksi.
Kannattaa mainita URL sekä leipätekstissä ("Comment") että kotisivun osoitteessa ("Homepage"), jotta sitä on helppo klikata. Yksikin lause sisällöstä tai jostain kiinostavasta huomiosta lisännee klikkauksia


# c.)


Attaaack! MITRE Attack Enterprise Matrix: Demonstroi viisi tekniikkaa viidestä eri taktiikasta.
Tekniikkaa tulee kokeilla käytännössä, kuvailu ei riitä. Asenna tarvittaessa omat harjoitusmaalit. Eristä tarvittaessa koneet Internetistä harjoittelun ajaksi. Voit käyttää kurssilla jo opeteltuja työkaluja (helpompaa) tai kokeilla uusia. Aiemminkin käytetyistä tekniikoista pitää tehdä uusi demonstraatio tässä tehtävässä. Mikäli haluat tehtävästä helpon version, tekniikoiden valinta auttaa. Tuolta löytyy myös tuttuja ja helppoja tekniikoita. Selitä, mitä esimerkissä tapahtuu. Nimeä käytetyt taktiikat, tekniikat ja alitekniikat. Merkitse myös numerot T0123.456.

# Templete injection (T1221)

Tein Portswigger Lab: Server-side template injection with information disclosure via user-supplied objects. Se on templete injection.

Serverin puoleinen mallin syöttöruiskutus (Server-Side Template Injection eli SSTI) on tietoturvaongelma, joka tapahtuu, kun hyökkääjä pystyy injektoimaan haitallista koodia palvelimen puoleisen mallin sisään. Tämä voi aiheuttaa erilaisia tietoturvariskejä, mukaan lukien tietojen paljastuminen. SSTI:n yhteydessä tietojen paljastuminen liittyy usein herkkien tietojen tai järjestelmätietojen käyttöön.

Syöttämällä {% debug %} -komento templateen edit-kohdassa tulee objektilista näkyviin.
Meillä on pääsy siihen. Pääsin settings-objektiin. Syöttämällä {{settings.SECRET_KEY}} komennon templateen editissä. Labra ratkaistu.





<img width="589" alt="Screenshot 2023-12-02 at 21 05 05" src="https://github.com/AkiAleksi/h6/assets/112399816/2371b25a-60e1-4331-82dd-7927185b34f9">




