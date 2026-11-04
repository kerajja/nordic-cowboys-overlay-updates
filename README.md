# Nordic Cowboys Overlay – päivityskanava

Tämä julkinen repositorio toimii Nordic Cowboys Overlayn virallisena päivityskanavana.

## Päivitysmanifesti

Asennettu Overlay tarkistaa tämän tiedoston HTTPS-yhteydellä noin 8 sekuntia käynnistyksen jälkeen:

`https://raw.githubusercontent.com/kerajja/nordic-cowboys-overlay-updates/main/latest.json`

Käyttäjä voi myös tarkistaa päivitykset overlayn hiiren oikean painikkeen valikosta.

Manifestin `status` on tällä hetkellä `setup`: ensimmäistä Setup.exe-julkaisua ei ole vielä julkaistu. Asiakasohjelma ei lataa mitään ennen kuin manifestin tila on `published`, versio on asennettua versiota uudempi, latausosoite on tämän repositorion GitHub Releases -osoite ja SHA-256 täsmää.

## Nykyinen asiakasversio

- Valmisteltu ohjelmaversio: **2.3.0**
- Julkaisun tila: **Windows-käännös ja testaus kesken**
- Jakelutiedosto: `Nordic Cowboys Overlay Setup.exe`
- Pakettityyppi: Inno Setup -asennusohjelma (EXE)

## Julkaisuprosessi

Lähdekoodipaketissa on kehittäjän työkalu `Publish-Update.ps1`. Kun uusi Setup.exe on rakennettu ja testattu, julkaisu tehdään GitHub CLI:llä. Skripti luo GitHub Releases -julkaisun, liittää Setup.exe:n ja päivittää latest.json-tiedoston vasta onnistuneen latauksen jälkeen. Katso `PUBLISHING.md` lähdekoodipaketista.

## Turvallisuus

- Lataukset hyväksytään vain tämän repositorion GitHub Releases -polusta HTTPS:n kautta.
- Jokaisen Setup.exe:n SHA-256 tarkistetaan ennen asennusohjelman käynnistystä.
- Pelin on oltava suljettuna, jotta telemetriaplugin voidaan päivittää.
- Älä tallenna GitHub-tokeneita tai salasanoja tähän julkiseen repositorioon.
- Älä muuta manifestin tilaa `published` ennen kuin vastaava julkaisuassetti on ladattu ja tarkistussumma on laskettu.
