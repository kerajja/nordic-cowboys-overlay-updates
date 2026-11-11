# Nordic Cowboys Overlay – julkaisuohjeet (Beta 14)

**Päivitetty 11.11.2026.** Tämä ohje koskee ensisijaisesti Beta-kanavaa. Stable 2.3.7:n julkaisu ja `main/latest.json` jätetään ennalleen.

## Beta 14:n julkaisutiedot

- Versio: `2.3.8-beta14`
- Tagi: `v2.3.8-beta14`
- Haara: `beta`
- Julkaisun nimi: `Nordic Cowboys Overlay Beta 2.3.8 Beta 14`
- Julkaisutyyppi: **Pre-release**
- Asennusassetin täsmällinen nimi: `Nordic.Cowboys.Overlay.Beta.Setup.exe`
- Julkaisuteksti: [BETA14_RELEASE_NOTES.md](BETA14_RELEASE_NOTES.md)
- Kaverin testi: [BETA14_UPDATE_TEST.md](BETA14_UPDATE_TEST.md)
- Tarkistuslista: [BETA14_RELEASE_CHECKLIST.md](BETA14_RELEASE_CHECKLIST.md)

## Ennen julkaisemista

1. Käännä **viimeisin toimivaksi ETS2:ssa testattu Beta 14** Windowsissa. Varmista, ettei kyse ole vanhasta Beta 7/11/13 -asentimesta. Uuden lähdekoodin julkaisupaketissa on `Build-Beta.bat`.
2. Testaa syntynyt `Nordic.Cowboys.Overlay.Beta.Setup.exe` Windowsissa. Tarkista, että versiona näkyy 2.3.8-beta14 ja että telemetria, mittarit, Discord sekä `TB CLIENT KÄYNNISSÄ` toimivat.
3. Tarkista, että `gh auth status` onnistuu. Asennus tarvitsee tarvittaessa `gh auth login` -kirjautumisen.
4. Kaverin koneelle pitää olla asennettu **2.3.8-beta13 ennen Beta 14:n julkaisua**, jos halutaan testata automaattista Beta 13 → Beta 14 -päivitystä.

## Julkaisu

**Suositus:** käytä lähdekoodipaketin `Publish-Beta14.bat`-skriptiä *vasta* onnistuneen käännöksen ja tarkistuksen jälkeen. Skriptin on julkaistava versionumerollinen Beta 14 -esijulkaisu, korvattava `beta-latest`-aliasjulkaisun asennusassetti ja päivitettävä **vain** `beta`-haaran `beta-latest.json` vasta kun assetit ovat valmiita.

Jos teet julkaisun käsin:

1. Avaa https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/new .
2. Luo uusi tagi `v2.3.8-beta14`, valitse kohdehaaraksi `beta`.
3. Syötä nimeksi `Nordic Cowboys Overlay Beta 2.3.8 Beta 14` ja liitä [julkaisutiedot](BETA14_RELEASE_NOTES.md).
4. Merkitse **Set as a pre-release** ja liitä *oikea* `Nordic.Cowboys.Overlay.Beta.Setup.exe`. Julkaise.
5. Päivitä erikseen `beta-latest`-esijulkaisun samanniminen assetti.
6. Laske SHA-256 Windowsissa komennolla `(Get-FileHash -Algorithm SHA256 '.\Nordic.Cowboys.Overlay.Beta.Setup.exe').Hash.ToLower()`.
7. Vasta kun **molemmat** julkaisujen assetit ovat saatavilla ja SHA-256 täsmää, päivitä `beta/beta-latest.json` versionumeroon `2.3.8-beta14`, status = `published`, `download_url` = versiojulkaisun suora asennus-URL, `sha256` = laskettu tarkistussumma, `published_at` = todellinen julkaisuhetki ja `release_notes` = lyhyt julkaisuteksti. Älä käytä arvattua SHA-arvoa.
8. Tarkista automaattipäivitys kaverin Beta 13 -asennuksesta.

**Älä muuta `main/latest.json`-tiedostoa, Stable-releasea tai `main`-haaraa Beta-julkaisun yhteydessä.**

## Julkaisun jälkeinen tarkistus

- [ ] `v2.3.8-beta14` on esijulkaisu ja oikea asennus-EXE on sen assettina.
- [ ] `beta-latest` on esijulkaisu ja sen assetilla on täsmälleen sama SHA-256.
- [ ] `beta/beta-latest.json` on tilassa `published` ja viittaa Beta 14:n versionumerolliseen julkaisuun.
- [ ] Tiedoston SHA-256 täsmää molempien release-assettien ja manifestin arvoihin.
- [ ] Beta 13 → Beta 14 -päivitystesti onnistuu myös toisella Windows-koneella.
- [ ] Stable 2.3.7:n `main/latest.json` on ennallaan.

Jos testi epäonnistuu, älä merkitse julkaisua valmiiksi. Korjaa Beta 14:n paketti; älä kytke Beta-virheen vuoksi Stable-päivityskanavaa uudelleen.
