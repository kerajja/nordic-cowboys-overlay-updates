# Nordic Cowboys Overlay – päivityskanava

Tämä julkinen repositorio toimii Nordic Cowboys Overlayn virallisena päivityskanavana.

## Päivitysmanifesti

Asennettu Overlay tarkistaa tämän tiedoston HTTPS-yhteydellä noin 8 sekuntia käynnistyksen jälkeen:

`https://raw.githubusercontent.com/kerajja/nordic-cowboys-overlay-updates/main/latest.json`

Käyttäjä voi myös tarkistaa päivitykset overlayn hiiren oikean painikkeen valikosta.

Manifestin `status` on tällä hetkellä `setup`: versiota 2.3.2 ei ole vielä julkaistu asennuspakettina. Asiakasohjelma ei lataa mitään ennen kuin manifestin tila on `published`, versio on asennettua versiota uudempi, latausosoite on tämän repositorion GitHub Releases -osoite ja SHA-256 täsmää.

## Valmisteltu versio 2.3.2

- Valvoo `TB Client.exe` -prosessia aktiivisen ETS2-keikan aikana.
- Jos TB Client puuttuu keikan alussa yli 15 sekuntia, näytetään varoitus.
- Jos prosessi katoaa kesken aktiivisen keikan yli 5 sekunniksi sen jälkeen, kun se on jo havaittu, näytetään punainen katkosvaroitus.
- Varoitus pysyy näkyvissä kyseisen keikan loppuun asti.
- Jos TB Client on käynnissä, overlay kertoo silti rehellisesti, ettei sen sisäistä tallennustilaa voida varmistaa.

**Rajoitus:** tämä ei vahvista TrucksBookiin kirjautumista, palvelinyhteyttä eikä sitä, että toimitus on palvelimella. TrucksBookin virallinen Wiki kertoo, että TB Client tukee offline-tilaa ja voi tallentaa toimituksia myöhempää lähetystä varten. Tarkempi tallennuksen vahvistus tarvitsee TrucksBookin dokumentoidun rajapinnan tai dokumentoidun stream-tiedostokentän.

## Julkaisuprosessi

Lähdekoodipaketissa on kehittäjän työkalu `Publish-Update.ps1`. Kun uusi Setup.exe on rakennettu ja testattu, julkaisu tehdään GitHub CLI:llä. Skripti luo GitHub Releases -julkaisun, liittää Setup.exe:n ja päivittää latest.json-tiedoston vasta onnistuneen latauksen jälkeen. Katso `PUBLISHING.md` lähdekoodipaketista.

## Turvallisuus

- Lataukset hyväksytään vain tämän repositorion GitHub Releases -polusta HTTPS:n kautta.
- Jokaisen Setup.exe:n SHA-256 tarkistetaan ennen asennusohjelman käynnistystä.
- Pelin on oltava suljettuna, jotta telemetriaplugin voidaan päivittää.
- Älä tallenna GitHub-tokeneita tai salasanoja tähän julkiseen repositorioon.
- Älä muuta manifestin tilaa `published` ennen kuin vastaava julkaisuassetti on ladattu ja tarkistussumma on laskettu.
