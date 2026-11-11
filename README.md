# Nordic Cowboys Overlay – virallinen päivityskanava

Tämä repositorio jakaa **Nordic Cowboys Overlayn** Windows-asennusohjelmat ja päivitysmanifestit. **Stable** ja **Beta** ovat erilliset kanavat.

## Nykyiset julkaisut (11.11.2026)

| Kanava | Nykyinen julkaistu versio | Manifesti |
| --- | --- | --- |
| Stable | [2.3.7](https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/tag/v2.3.7) | [`main/latest.json`](https://github.com/kerajja/nordic-cowboys-overlay-updates/blob/main/latest.json) |
| Beta | [2.3.8-beta13](https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/tag/v2.3.8-beta13) | [`beta/beta-latest.json`](https://github.com/kerajja/nordic-cowboys-overlay-updates/blob/beta/beta-latest.json) |

**Beta 14 on valmistelussa**, eikä sitä merkitä julkaistuksi ennen kuin sen oikea Windows-asennusohjelma on GitHub Releases -palvelussa ja tarkistussummat täsmäävät.

- Pysyvä Beta-asentimen osoite: https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/download/beta-latest/Nordic.Cowboys.Overlay.Beta.Setup.exe
- Stable-päivitysmanifesti: https://raw.githubusercontent.com/kerajja/nordic-cowboys-overlay-updates/main/latest.json
- Beta-päivitysmanifesti: https://raw.githubusercontent.com/kerajja/nordic-cowboys-overlay-updates/beta/beta-latest.json

## Beta 14:n julkaiseminen

- [Julkaisutiedot](BETA14_RELEASE_NOTES.md)
- [Julkaisun tarkistuslista](BETA14_RELEASE_CHECKLIST.md)
- [Beta 13 → Beta 14 -automaattipäivityksen testi](BETA14_UPDATE_TEST.md)
- [Yleiset julkaisuohjeet](PUBLISHING.md)

Beta 14:n automaattista lauttareitin ennakkotunnistusta **ei ole vielä toteutettu valmiiksi**; tämä rajoitus ilmoitetaan julkaisutiedoissa.

## Päivitysten turvallisuus

Asiakas hyväksyy vain julkaistun ja versionumeroltaan uudemman manifestimerkinnän. Asennusohjelman latausosoitteen on osoitettava tämän repositorion GitHub Releases -lataukseen ja SHA-256-tiivisteen täsmättävä ennen asennusta.

TrucksBookin paikallisia lokeja ei lähetetä GitHubiin. Älä tallenna GitHub-tokeneita, salasanoja tai käyttäjien diagnostisia lokeja julkiseen repositorioon.

**Beta-julkaisu ei muuta Stable 2.3.7:n `main/latest.json`-tiedostoa.**
