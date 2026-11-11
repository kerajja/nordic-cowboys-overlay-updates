# Nordic Cowboys Overlay 2.3.8 Beta 14

**Esijulkaisu – 11.11.2026**

## Uutta ja korjattua

- Valittavat matka- ja polttoainemittarit: ajettu matka, kulutettu polttoaine, keskikulutus, polttoainemäärä, tankin täyttöaste ja arvioitu toimintamatka.
- Nopeus ja keskinopeus omissa, samankokoisissa mittarikentissään. Keskinopeuden laskentaa on korjattu.
- Automaattisesti mukautuva mittaristo: lisämittarit laajentavat overlayta sivusuunnassa.
- Keikkapohjaiset ajotilastot nollautuvat uuden keikan alussa; tankkaus, pysähdykset ja teleporttaus huomioidaan laskennassa.
- Keikan tila alareunassa TrucksBook-lähetystiedon jatkona.
- Cowboy-taukoteksti, kun aktiivista keikkaa tai GPS-reittiä ei ole. Sama viesti pysyy tauon ajan ja vaihtuu seuraavan keikan jälkeen.
- Erillinen Beta-telemetrialisäosa, jotta lisämittarit toimivat Stablea muuttamatta.
- Discord Rich Presence -tuki säilyy.

## Tiedossa olevat rajoitukset

- **Automaattinen lauttamatkan vähennys ei vielä tunnista ETS2:n valitsemaa lauttareittiä luotettavasti.** Tätä ominaisuutta ei pidä tulkita valmiiksi.
- Discordissa käytössä olevan HaulMP-/TruckersMP-palvelimen nimen automaattinen tunnistus ei ole vielä kaikissa tilanteissa varmennettu.
- Kyseessä on kokeellinen **Beta**, ei Stable-päivitys.

## Asennus

Sulje Nordic Cowboys Overlay Beta sekä ETS2 ja HaulMP/TruckersMP ennen asennusta. Lataa tämän GitHub-julkaisun tiedosto `Nordic.Cowboys.Overlay.Beta.Setup.exe`, suorita asennus ja käynnistä peli uudelleen. Beta asentuu erikseen Stable-versiosta.

## Beta-päivityksen testaus

Jos sinulla on jo **2.3.8-beta13**, älä asenna Beta 14:ää käsin: avaa vanha Beta 13, jotta automaattinen päivitys voidaan testata. Sulje ETS2, jos päivitys odottaa pelin sulkemista. Tarkista päivityksen jälkeen, että versio on **2.3.8-beta14**.

**Stable 2.3.7 ja sen `latest.json`-päivityskanava pysyvät ennallaan.**
