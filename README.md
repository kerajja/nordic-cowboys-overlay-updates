# Nordic Cowboys Overlay – päivityskanava

Tämä julkinen repositorio toimii Nordic Cowboys Overlayn virallisena päivityskanavana.

## Päivitysmanifesti

Asennettu Overlay tarkistaa tämän tiedoston HTTPS-yhteydellä noin 8 sekuntia käynnistyksen jälkeen:

`https://raw.githubusercontent.com/kerajja/nordic-cowboys-overlay-updates/main/latest.json`

Käyttäjä voi myös tarkistaa päivitykset overlayn hiiren oikean painikkeen valikosta.

Manifestin `status` on tällä hetkellä `setup`: versiota 2.3.4 ei ole vielä julkaistu asennuspakettina. Asiakasohjelma ei lataa mitään ennen kuin manifestin tila on `published`, versio on asennettua versiota uudempi, latausosoite on tämän repositorion GitHub Releases -osoite ja SHA-256 täsmää.

## Valmisteltu versio 2.3.4 – TrucksBook-lokipolun korjaus

- Etsii TrucksBook Clientin `log.txt`-tiedoston käyttäjän `%LOCALAPPDATA%\TrucksBook`-kansiosta ja enintään viiden alikansiotason syvyydeltä.
- Jos tiedostoja on useita, valitsee viimeksi muokatun.
- Vanha `C:\Users\Public\Documents\TB Client\log.txt` -sijainti toimii varalla.
- Tunnistaa `Starting delivery` ja `Delivery exist, continue` -tapahtumista aktiivisen toimituksen.
- Tunnistaa `Delivered`-tapahtuman ja näyttää toimituksen odottavan lähetystä.
- Tunnistaa `Try upload file` -tapahtuman lähetysyrityksen.
- Näyttää lähetyksen vahvistetuksi vasta, kun lokissa on `File is uploaded, delivery ID ...`.
- Lokitiedoston sisältöä käsitellään vain paikallisesti. Sitä ei kopioida päivityspalveluun eikä lisätä GitHubiin.

**Rajoitukset:** tunnistus perustuu TrucksBook Client 1.5.x -lokissa havaittuihin riveihin. Jos TrucksBook muuttaa lokimuotoa, parseri saattaa vaatia päivityksen. `File is uploaded` on TB Clientin oma lokiin kirjaama lähetyskuittaus; se ei ole erillinen VTC:n hyväksyntäkuittaus.

## Julkaisuprosessi

Lähdekoodipaketissa on kehittäjän työkalu `Publish-Update.ps1`. Kun uusi Setup.exe on rakennettu ja testattu, julkaisu tehdään GitHub CLI:llä. Skripti luo GitHub Releases -julkaisun, liittää Setup.exe:n ja päivittää latest.json-tiedoston vasta onnistuneen latauksen jälkeen. Katso `PUBLISHING.md` lähdekoodipaketista.

## Turvallisuus

- Lataukset hyväksytään vain tämän repositorion GitHub Releases -polusta HTTPS:n kautta.
- Jokaisen Setup.exe:n SHA-256 tarkistetaan ennen asennusohjelman käynnistystä.
- Pelin on oltava suljettuna, jotta telemetriaplugin voidaan päivittää.
- TrucksBookin loki luetaan paikallisesti eikä sitä lähetetä ulos.
- Älä tallenna GitHub-tokeneita, salasanoja tai diagnostisia lokeja tähän julkiseen repositorioon.
- Älä muuta manifestin tilaa `published` ennen kuin vastaava julkaisuassetti on ladattu ja tarkistussumma on laskettu.
