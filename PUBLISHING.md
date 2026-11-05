# Julkaisuohje – Nordic Cowboys Overlay 2.3.4

## Betan pysyvä latauslinkki ja julkaisu

Beta-asentimen pysyvä latausosoite on:

https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/download/beta-latest/Nordic.Cowboys.Overlay.Beta.Setup.exe

Osoite käyttää erillistä `beta-latest`-esijulkaisua. Stable ei käytä tätä aliasia, eikä sen `latest.json`-manifestia päivitetä Beta-julkaisun yhteydessä.

Kun julkaiset uuden Betan lähdekoodipaketin `Publish-Beta-Update.ps1`-skriptillä, se luo tai päivittää versionumerollisen Beta-julkaisun, korvaa saman nimisen asentimen `beta-latest`-aliasjulkaisussa ja päivittää lopuksi vain beta-haaran `beta-latest.json`-manifestin. Skripti tarkistaa ennen aliasin muuttamista, että alias on edelleen esijulkaisu. Pysyvä latauslinkki pysyy näin samana mutta sen tiedosto vaihtuu uusimpaan Betaan.

Julkaisun jälkeen tarkista, että `beta-latest`-julkaisun asentimen SHA-256 täsmää versionumerollisen Beta-julkaisun ja `beta-latest.json`-manifestin SHA-256-arvon kanssa.

## Stable-julkaisun tarkistusohje

Asennusohjelma on saatu ja tarkistettu:
- Tiedosto: `Nordic Cowboys Overlay Setup.exe`
- Sisäinen tuoteversio: `2.3.4`
- Tiedostokoko: 2,214,852 tavua
- SHA-256: `aa7d313fefc46df731881b74cee21fe9a8c53e192540bf4cc1e2e93e78728efb`

Manifesti `latest.json` sisältää jo versionumeron ja SHA-256:n, mutta `status` pysyy arvossa `setup`, kunnes EXE on GitHub Release -assetina. Älä vaihda tilaa ennen kuin lataus on olemassa.

## Luo GitHub Release selaimessa

1. Avaa: https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/new
2. Luo uusi tagi: `v2.3.4`.
3. Julkaisun otsikko: `Nordic Cowboys Overlay 2.3.4`.
4. Lisää julkaisuun alla olevat julkaisutiedot.
5. Lataa assetiksi täsmälleen `Nordic Cowboys Overlay Setup.exe`.
6. Julkaise Release.
7. Avaa julkaistu Release, napsauta EXE-assettia hiiren oikealla ja kopioi linkin osoite. Varmista, että se on suora `https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/download/v2.3.4/...` -osoite.
8. Päivitä `latest.json`: `status` = `published`, `download_url` = kopioitu suora asset-osoite, `published_at` = julkaisupäivä ISO 8601 -muodossa. Säilytä SHA-256 sellaisenaan.

## Julkaisutiedot

```markdown
## Nordic Cowboys Overlay 2.3.4

- TrucksBook-keikan tunnistus paikallisesta Client-lokista.
- Lokitiedoston automaattinen etsintä käyttäjän %LOCALAPPDATA%\\TrucksBook-kansiosta ja alikansioista.
- Toimituksen lähetyksen vahvistus näytetään vasta, kun TrucksBook Client kirjaa TB ID:n.
- Lokitiedosto käsitellään paikallisesti; sitä ei lähetetä päivityspalveluun.

Asennus: lataa Setup.exe ja suorita se, kun ETS2 on suljettu.
```

## Komentorivi vaihtoehtona

Jos GitHub CLI on asennettu ja kirjautuminen tehty (`gh auth login`), Release voidaan luoda komennolla:

```powershell
gh release create v2.3.4 `.\\Nordic Cowboys Overlay Setup.exe` --title `"Nordic Cowboys Overlay 2.3.4`" --notes `"TrucksBook-keikan tunnistus, paikallinen lokinluku sekä toimituksen TB ID -lähetysvahvistus.`"
```

Sen jälkeen kopioi assetin todellinen URL Release-sivulta ja päivitä `latest.json` vasta kun lataus toimii.

## Asiakkaiden päivitys

Overlay tarkistaa manifestin käynnistyksen jälkeen ja oikean hiiren painikkeen valikon komennolla **Tarkista päivitykset**. Se hyväksyy vain tämän repositorion Releases-polusta tulevan asennusohjelman, ja tarkistaa SHA-256-summan ennen käynnistämistä.

Ensimmäinen päivitys vanhemmasta versiosta on asennettava manuaalisesti käyttäjille, joiden overlayssa ei vielä ole päivitystarkistinta. Tämän jälkeen tuetut versiot voivat käyttää sovelluksen omaa päivitystoimintoa.
