# Nordic Cowboys Overlay – päivityskanava

Tämä julkinen repositorio toimii Nordic Cowboys Overlayn päivitysten jakelukanavana.

## Julkinen päivitysmanifesti

Overlayn päivitystarkistin lukee tämän tiedoston:

`https://raw.githubusercontent.com/kerajja/nordic-cowboys-overlay-updates/main/latest.json`

Manifesti sisältää viimeisimmän julkaistun version, päivityspaketin latausosoitteen ja SHA-256-tarkistussumman.

## Julkaisun työnkulku

1. Rakenna Windowsissa uusi Overlay EXE ja NCOTelemetry DLL.
2. Pakkaa päivitettävät tiedostot yhteen ZIP-pakettiin. Älä sisällytä henkilökohtaisia tietoja tai salaisuuksia.
3. Julkaise ZIP GitHub Releases -julkaisun liitteenä.
4. Laske ZIP-paketin SHA-256-tarkistussumma.
5. Päivitä `latest.json` vasta, kun julkaisu ja ladattava tiedosto ovat saatavilla.
6. Asiakasohjelma tarkistaa manifestin, vertaa versiota ja tarkistaa latauksen SHA-256:n ennen asennusta.

## Tärkeä nykytila

Päivityskanava on alustettu, mutta automaattinen päivitys ei ole vielä valmis pelkästään tämän repositorion luomisen ansiosta. Overlayn EXE:en täytyy lisätä päivitystarkistin ja turvallinen päivitysapuri. Julkaisupaketti sekä sen todellinen latausosoite ja SHA-256 lisätään ennen ensimmäistä päivitysjulkaisua.

## Turvallisuus

- Älä koskaan tallenna GitHub-tokenia, salasanaa tai muuta salaista tietoa tähän repositorioon.
- Asiakasohjelman tulee hyväksyä päivitys vain HTTPS-yhteydestä ja tarkistaa SHA-256 ennen tiedostojen käyttöönottoa.
- Päivitys tulee asentaa vasta, kun Overlay ja peliin ladattu telemetriaplugin voidaan turvallisesti sulkea/päivittää.
- Manifestin muuttaminen ei yksin julkaise ohjelmaa. Julkaisun ZIP-liite on luotava ja tarkistettava erikseen.
