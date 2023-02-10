# Jakelun luominen

Python-sovellus vaatii käyttäjältä Python-tulkin toimiakseen. Jos halutaan tehdä ilman tulkkia toimiva sovellus, luodaan asennuspaketti, joka sisältää Python-linkkikirjaston (dll) ja tarvittavat Python-kirjastot ja -modulit sekä muut sovelluksen käyttämät tiedostot. Asennuspaketin lisäksi voidaan luoda asennusohjelma (installer).

## Jakelu Github-repositoriosta

## Työvaiheet
1. Kloonataan repositorio paikalliselle koneelle
2. Luodaan Python-virtuaaliympäristö
3. Päivitetään `pip` uusimpaan versioon
4. Ladataan tarvittavat ulkoiset kirjastot `pip`-komentojen avulla

### Virtuaaliympäristön luominen
Jotta sovelluksen vaatimat kirjastot eivät sotkisi koneen muiden Python-ohjelmien toimintaa, luodaan virtuaaliympäristö, jonka Python-tulkkia käytetään sovelluksen ohjelmoinnissa, ja johon lisäkirjastot asennetaan.
Virtuaaliympäristö luodaan terminaalissa komennolla `python -m venv venv`. Komento luo hakemiston `venv`. Sen alihakemistosta löytyy aktivointikomento `Activate.ps1` joka käynnistetään terminaalissa komennolla `...\venv\Scripts> .\Activate`. Merkintä `...` tarkoittaa polun alkuosaa, joka riippuu siitä, mihin hakemistoon repositorio on kloonattu. Aktivoinnin jälkeen vaihdetaan Python-tulkiksi `venv`-hakemiston Python tulkki:

![image](https://user-images.githubusercontent.com/24242044/218056845-51bf3a58-7521-4651-b92a-bd75e5f49797.png)

### Kirjastojen lataaminen
Sovellus saattaa käyttää kirjastoja. Python-terminologiassa kaikki Python-tiedostot, joita ohjelma käyttää, ovat moduuleja (module). Yleisesti käytetään kuitenkin termiä kirjasto, kun tarkoitetaan erikseen ladattavaa Python tiedostoa, jonka joku toinen on kirjoittanut yleiseen käyttöön. Kirjasto voi olla ulkoinen kirjasto, joka on otettava käyttöön erikseen asentamalla tai sisäinen kirjasto, joko tulee Python-tulkin mukana.

Esimerkiksi jos sovellus tarvitsee **Qt**-käyttöliittymän kirjastoja, ne asennetaan komennolla `pip install PyQt5`. Ennen kirjastojen asennusta kannattaa päivittää kirjastojen asennusohjelma komennolla `pip install --upgrade pip`.

