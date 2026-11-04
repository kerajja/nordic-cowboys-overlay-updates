# Nordic Cowboys Overlay – päivityskanava

Tämä julkinen repositorio toimii Nordic Cowboys Overlayn virallisena päivityskanavana.

## Päivitysmanifesti

Asennettu Overlay tarkistaa tämän tiedoston HTTPS-yhteydellä noin 8 sekuntia käynnistyksen jälkeen:

`https://raw.githubusercontent.com/kerajja/nordic-cowboys-overlay-updates/main/latest.json`

Käyttäjä voi myös tarkistaa päivitykset overlayn hiiren oikean painikkeen valikosta.

Manifestissa valmisteltu versio on **2.3.4**. Sen Windows-asennusohjelman sisäinen versiotieto ja SHA-256-tarkistussumma on tarkistettu. Manifestin tila on edelleen `setup`, koska GitHub Release -julkaisun binääriassetti on lataamatta. Asiakasohjelma ei lataa mitään ennen kuin tila on `published`, download_url osoittaa tämän repositorion GitHub Release -assettiin ja SHA-256 täsmää.

## Versio 2.3.4 – TrucksBook Sync

- Etsii TrucksBook Clientin `log.txt`-tiedoston käyttäjän `%LOCALAPPDATA%\TrucksBook`-kansiosta ja alikansioista.
- Tunnistaa aktiivisen keikan lokimerkinnöistä.
- Näyttää toimituksen lähetyksen odottavana, kunnes lokissa näkyy TrucksBook Clientin vahvistus `File is uploaded, delivery ID ...`.
- Näyttää toimituksen TB ID:n lähetyksen jälkeen.
- Lukee lokitiedoston paikallisesti. Lokin sisältöä ei lähetetä päivityspalveluun eikä lisätä GitHubiin.

**Testaus:** käyttäjä on testannut version 2.3.4 Windows-koneellaan. Kuvakaappauksissa näkyvät sekä aktiivisen TrucksBook-keikan tunnistus että onnistuneen lähetyksen TB ID.

**Rajoitukset:** tunnistus perustuu TrucksBook Clientin lokimuotoon. Jos TrucksBook muuttaa lokimerkintöjä, parseri voi vaatia päivityksen. `File is uploaded` on TB Clientin oma lokiin kirjaama lähetyskuittaus; se ei ole erillinen VTC:n hyväksyntäkuittaus.

## Julkaiseminen

Julkaise tagi `v2.3.4` GitHub Releases -sivulla ja liitä mukaan tiedosto `Nordic Cowboys Overlay Setup.exe`. Laske tai tarkista sen SHA-256. Päivitä vasta tämän jälkeen `latest.json`:
- `status`: `published`
- `download_url`: julkaistun EXE-assetin suora selainlatausosoite
- `sha256`: tarkistussumma (manifestissa valmiina, jos assetti ei muutu)
- `published_at`: julkaisupäivä ISO 8601 -muodossa

Katso tarkemmat ohjeet tiedostosta `PUBLISHING.md`.

## Turvallisuus

- Lataukset hyväksytään vain tämän repositorion GitHub Releases -polusta HTTPS:n kautta.
- Jokaisen Setup.exe:n SHA-256 tarkistetaan ennen asennusohjelman käynnistystä.
- Pelin on oltava suljettuna, jotta telemetriaplugin voidaan päivittää.
- TrucksBookin loki luetaan paikallisesti eikä sitä lähetetä ulos.
- Älä tallenna GitHub-tokeneita, salasanoja tai diagnostisia lokeja tähän julkiseen repositorioon.
- Älä muuta manifestin tilaa `published` ennen kuin vastaava julkaisuassetti on ladattu ja tarkistussumma on laskettu.
