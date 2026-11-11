# Nordic Cowboys Overlay – Beta 13 → Beta 14 -automaattipäivityksen testi

**Tavoite:** varmistaa, että aiemmin asennettu 2.3.8-beta13 löytää GitHubiin julkaistun 2.3.8-beta14:n, lataa sen, tarkistaa SHA-256:n, asentaa ja käynnistää uuden version.

## Ennen Beta 14:n julkaisemista
1. Lataa ja asenna virallinen Beta 13: https://github.com/kerajja/nordic-cowboys-overlay-updates/releases/tag/v2.3.8-beta13
2. Avaa NCO Beta ja varmista asetuksista / päivitysnäkymästä, että versio on 2.3.8-beta13.
3. Älä asenna Beta 14:ää itse. Sulje ETS2, HaulMP ja TruckersMP.

## Kun Beta 14 on julkaistu GitHubiin
4. Avaa aiemmin asennettu Beta 13.
5. Seuraa automaattista päivitystarkistusta. Jos päivitys ei ala, avaa F9 → Päivitykset → Tarkista päivitykset.
6. Tarkista, että päivitys löytää version 2.3.8-beta14, lataa asennusohjelman ja aloittaa asennuksen. Jos ETS2 on auki, sulje peli ja anna päivityksen jatkua.
7. Varmista, että NCO käynnistyy uudelleen ja näyttää version 2.3.8-beta14.
8. Käynnistä ETS2/HaulMP ja tarkista nopeus, keskinopeus, lisämittarit, keikan tilarivi ja ettei TB CLIENT KÄYNNISSÄ -ilmaisin muutu.
9. Avaa F9 → Päivitykset vielä kerran. Sen pitää ilmoittaa, että käytössä on uusin Beta.

## Raportoi testistä
- Lähtöversio: 2.3.8-beta13 / muu:
- Havaitsiko Beta 14:n automaattisesti: kyllä / ei
- Lataus ja tarkistussumma: onnistui / epäonnistui
- Asennus ja uudelleenkäynnistys: onnistui / epäonnistui
- Lopullinen versio: 
- Toimiiko telemetria: kyllä / ei
- Mitä päivitysnäkymässä luki mahdollisen virheen aikana:
- Kuvakaappaus tai virheloki (jos virhe):

Huomio: Beta14 on julkaistu vasta, kun oikea asennin löytyy v2.3.8-beta14-julkaisusta, pysyvä beta-latest-linkki on päivitetty ja beta-haaran beta-latest.json viittaa samaan asennintiedostoon ja SHA-256-tiivisteeseen. Stableen ei kosketa.
