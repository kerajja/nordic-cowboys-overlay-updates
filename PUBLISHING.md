# Julkaisuohje – Nordic Cowboys Overlay

## Nykytila

Päivityskanava on luotu. `latest.json` on tarkoituksella tilassa `setup`, joten asiakkaat eivät lataa päivitystä ennen kuin ensimmäinen testattu asennuspaketti on julkaistu.

## Versio 2.3.0

1. Rakenna ohjelma Windowsissa lähdekoodipaketin `Build.bat`-tiedostolla.
2. Testaa Setup.exe omalla koneella: asennus, ETS2-telemetria, keikkatiedot, ylinopeusmuisti ja päivitystarkistus.
3. Asenna GitHub CLI: https://cli.github.com/
4. Kirjaudu: `gh auth login`
5. Aja projektikansiosta `Publish-Update.ps1`.

Julkaisuskripti luo version mukaisen GitHub Releases -julkaisun, lataa `Nordic Cowboys Overlay Setup.exe` -assetin, laskee SHA-256-tarkistussumman ja päivittää `latest.json`-manifestin viimeisenä.

## Asiakkaan päivitys

Overlay tarkistaa manifestin käynnistyksen jälkeen ja oikean hiiren painikkeen valikon komennolla **Tarkista päivitykset**. Se lataa vain tämän repositorion Releases-polusta ja tarkistaa asennusohjelman SHA-256-summan ennen käynnistämistä.

Ensimmäinen 2.3.0-asennus on asennettava kerran manuaalisesti kaikille nykyisille 2.2.9-käyttäjille, koska vanhassa versiossa ei ole päivitystarkistinta. Sen jälkeen tulevat versiot voidaan toimittaa sovelluksen oman päivitystoiminnon kautta.
