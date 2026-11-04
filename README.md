# Nordic Cowboys Overlay – päivityskanava

Tämä julkinen repositorio toimii Nordic Cowboys Overlayn virallisena päivityskanavana.

## Julkaistu versio 2.3.5

<https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/tag/v2.3.5>

Versio 2.3.5 on julkaistu GitHub Releases -palvelussa. Asennusohjelman SHA-256 täsmää julkaisuassettiin, ja `latest.json` on tilassa `published`.

## Päivitysmanifesti

Asennettu Overlay tarkistaa tämän tiedoston HTTPS-yhteydellä noin 8 sekuntia käynnistyksen jälkeen:

`https://raw.githubusercontent.com/kerajja/nordic-cowboys-overlay-updates/main/latest.json`

Käyttäjä voi myös tarkistaa päivitykset overlayn hiiren oikean painikkeen valikosta.

Manifesti sisältää version, suoran latausosoitteen ja SHA-256-tarkistussumman. Asiakasohjelman tulee hyväksyä päivitys vain, kun tila on `published`, versio on asennettua versiota uudempi, latausosoite on tämän repositorion GitHub Releases -osoite ja SHA-256 täsmää.

## Versio 2.3.5 – julkaistut parannukset

- Taustapuskuripiirto vähentää overlayn välkkymistä.
- TrucksBookin tila- ja ilmoitustekstit ovat aiempaa suuremmat.
- ETS2-prosessin käynnistysvahti avaa overlayn automaattisesti pelin käynnistyessä.
- Overlay muistaa käyttäjän valitseman näyttösijainnin.
- Nordic Cowboys VTC -yrityslogo on sovelluksen ja pikakuvakkeiden kuvakkeena läpinäkyvällä taustalla.
- TrucksBook Sync tunnistaa aktiivisen keikan sekä TB Clientin lokiin kirjaaman lähetyskuittauksen ja näyttää TB ID:n.

Lokitiedosto käsitellään paikallisesti. Sen sisältöä ei lähetetä päivityspalveluun eikä lisätä GitHubiin.

**Rajoitukset:** TrucksBook-tunnistus perustuu Clientin lokimuotoon. Jos TrucksBook muuttaa lokimerkintöjä, parseri voi vaatia päivityksen. `File is uploaded` on TB Clientin oma lokiin kirjaama lähetyskuittaus; se ei ole erillinen VTC:n hyväksyntäkuittaus. ETS2-automaattikäynnistys edellyttää, että taustavahti on asennettu ja automaattikäynnistys sallittu.

## Turvallisuus

- Lataukset hyväksytään vain tämän repositorion GitHub Releases -polusta HTTPS:n kautta.
- Jokaisen Setup.exe:n SHA-256 tarkistetaan ennen asennusohjelman käynnistystä.
- Pelin on oltava suljettuna, jotta telemetriaplugin voidaan päivittää.
- TrucksBookin loki luetaan paikallisesti eikä sitä lähetetä ulos.
- Älä tallenna GitHub-tokeneita, salasanoja tai diagnostisia lokeja tähän julkiseen repositorioon.
