# Beta 14 – viimeistely ja julkaisun tarkistuslista

Tämä tarkistuslista on tarkoituksella **keskeneräinen**, kunnes oikea Windows-asennin on ladattu GitHubiin. Pelkkä lähdekoodi-ZIP tai julkaisuteksti ei ole valmis julkaisu.

## Valmis GitHubissa

- [x] Beta 14:n julkaisutiedot kirjoitettu: [BETA14_RELEASE_NOTES.md](BETA14_RELEASE_NOTES.md)
- [x] Kaverin automaattipäivityksen testiohje kirjoitettu: [BETA14_UPDATE_TEST.md](BETA14_UPDATE_TEST.md)
- [x] Beta-/Stable-kanavien erottelu dokumentoitu: [PUBLISHING.md](PUBLISHING.md)
- [x] Beta 13:n päivitysmanifesti jätetty toimivaksi ja koskemattomaksi odottamaan Beta 14:n asenninta

## Vielä tehtävä Windowsissa

- [ ] Käännä **viimeisin toimivaksi todettu Beta 14**: `Build-Beta.bat`
- [ ] Varmista, että tuloksena on `Nordic.Cowboys.Overlay.Beta.Setup.exe` ja versio on `2.3.8-beta14`
- [ ] Testaa Beta 14:n asennus ja telemetria, nopeus/keskinopeus, mittarit, Cowboy-tekstit, Discord sekä TrucksBook
- [ ] Varmista, että kaveri on asentanut Beta 13:n ja sulkenut sen ennen julkaisua
- [ ] Julkaise **v2.3.8-beta14** esijulkaisuna, oikea asennin assettina
- [ ] Päivitä **beta-latest**-esijulkaisun asennin samaan tiedostoon
- [ ] Varmista molempien release-assettien SHA-256-yhteneväisyys
- [ ] Päivitä vain **beta/beta-latest.json** (versio, URL, SHA-256, julkaisuhetki)
- [ ] Kaveri avaa Beta 13:n, testaa löytymisen, latauksen, asennuksen ja uudelleenkäynnistyksen
- [ ] Varmista, että päivittynyt ohjelma näyttää `2.3.8-beta14`
- [ ] Varmista, että Stable 2.3.7 ei ole muuttunut

## Suorat linkit

- Luo julkaisu: https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/new
- Beta 13: https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/tag/v2.3.8-beta13
- Beta 14 -tagi (toimii vasta julkaisun jälkeen): https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/tag/v2.3.8-beta14
- Beta-alias: https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/tag/beta-latest
- Beta-manifesti: https://github.com/kerajja/nordic-cowboys-overlay-updates/blob/beta/beta-latest.json

**Tiedossa oleva rajoitus:** automaattinen lauttareitin ennakkotunnistus on vielä kesken. Älä ilmoita sen olevan valmis Beta 14:ssä.
