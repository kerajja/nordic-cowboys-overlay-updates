# Nordic Cowboys Overlay – päivityskanava

Tämä julkinen repositorio toimii Nordic Cowboys Overlayn virallisena päivityskanavana.

## Julkaistu versio 2.3.4

<https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/tag/v2.3.4>

Versio 2.3.4 on julkaistu GitHub Releases -palvelussa. Asennusohjelman SHA-256 on tarkistettu, ja `latest.json` on tilassa `published`.

## Päivitysmanifesti

Asennettu Overlay tarkistaa tämän tiedoston HTTPS-yhteydellä noin 8 sekuntia käynnistyksen jälkeen:

`https://raw.githubusercontent.com/kerajja/nordic-cowboys-overlay-updates/main/latest.json`

Käyttäjä voi myös tarkistaa päivitykset overlayn hiiren oikean painikkeen valikosta.

Manifesti sisältää version, suoran latausosoitteen ja SHA-256-tarkistussumman. Asiakasohjelman tulee hyväksyä päivitys vain, kun tila on `published`, versio on asennettua versiota uudempi, latausosoite on tämän repositorion GitHub Releases -osoite ja SHA-256 täsmää.

## Versio 2.3.4 – TrucksBook Sync

- Etsii TrucksBook Clientin `log.txt`-tiedoston käyttäjän `%LOCALAPPDATA%\TrucksBook`-kansiosta ja alikansioista.
- Tunnistaa aktiivisen keikan lokimerkinnöistä.
- Näyttää toimituksen lähetyksen odottavana, kunnes lokissa näkyy TrucksBook Clientin vahvistus `File is uploaded, delivery ID ...`.
- Näyttää toimituksen TB ID:n lähetyksen jälkeen.
- Lukee lokitiedoston paikallisesti. Lokin sisältöä ei lähetetä päivityspalveluun eikä lisätä GitHubiin.

**Testaus:** käyttäjä on testannut version 2.3.4 Windows-koneellaan. Testikuvissa näkyvät sekä aktiivisen TrucksBook-keikan tunnistus että onnistuneen lähetyksen TB ID.

**Rajoitukset:** tunnistus perustuu TrucksBook Clientin lokimuotoon. Jos TrucksBook muuttaa lokimerkintöjä, parseri voi vaatia päivityksen. `File is uploaded` on TB Clientin oma lokiin kirjaama lähetyskuittaus; se ei ole erillinen VTC:n hyväksyntäkuittaus.

## Turvallisuus

- Lataukset hyväksytään vain tämän repositorion GitHub Releases -polusta HTTPS:n kautta.
- Jokaisen Setup.exe:n SHA-256 tarkistetaan ennen asennusohjelman käynnistystä.
- Pelin on oltava suljettuna, jotta telemetriaplugin voidaan päivittää.
- TrucksBookin loki luetaan paikallisesti eikä sitä lähetetä ulos.
- Älä tallenna GitHub-tokeneita, salasanoja tai diagnostisia lokeja tähän julkiseen repositorioon.
