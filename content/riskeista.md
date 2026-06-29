---
title: "Riskeistä"
---


Lääkinnällisiä laitteita koskevaan tietoon kohdistuu voimakas tiedon tarkkuuden ja oikeellisuuden vaatimus. 

Keskeinen riskitekijä [[llm-wiki|LLM-wiki]] -ratkaisussa on tekoälyagentin tekemä tiivistys lähdedokumenttien perusteella. Tämä tiivistys voi sisältää virheitä ja hallusinointia. 

Riskin mitigoinnissa keskeistä on:

#### 1) Vastuiden kuvaaminen ####

Valmistaja on vastuussa julkaisusta tiedosta, ei tekoälyagentti ja tekoälyagentin takana oleva laaja kielimalli. Käytetty tekoälyratkaisu tulee sisäisesti vastuuttaa henkilölle. 

#### 2) Tekoälyn ohjeistus ####

Ohjeistuksen tulee sisältää ohjeet, jotka kieltävät väitteet ja päätelmät, jotka eivät suoraan perustu lähteisiin. Tämä toki ei ole yksinkertainen asia, koska tekoälyä nimenomaan pyydetään tiivistämään alkuperäistä sisältöä.

Työskentelytapaan liittyvä ohjeistus puolestaan on, että tekoälyn tulee sisällön luomisen yhteydessä kysyä lupaa asiantuntijalta ainakin tapaukissa, jossa sisältöö liittyy erityisiä tekoälyn tunnistamia ongelmia. 

Sisällön tuottamisessa tulee  käyttää käyttää korkeatasoista laajaa kielimallia mini- tai nanomallien sijaan. 

#### 3) Tarkastus-työnkulut ####

Sisällön tuottamisen jälkeen tulee tekoäly ohjeistaa tarkastamaan sisältö ja tunnistamaan mahdolliset virheet ja puutteet. Tällaisia voivat olla mm.
- väitteet, joihin ei löydy lähdettä
- toistensa kanssa ristiriitaiset sisällöt
- oletetut, mutta puuttuvat sisällöt
- jne.

Tämän sivuston esimerkkinä virheiden ja puutteiden tunnistamisesta ovat [[muutostarpeet-koonti|Muutostarpeet]]. 

#### 4) Lähteet esille ####

Sisällön tulee osoittaa lähteisiin, jolloin sisältöä voi arvioida suhteessa lähteisiin. 

Koska valmistajalla on tekijänoikeus sisältöihin, on myös mahdollista, että itse wiki:ssä on erillinen sivu, jossa on alkuperäinen teksti.

#### 5) Asiantuntija tarkastajana ####

Vaikka agentti tuottaa sivuston, tulee asiantuntijan tarkastaa ja hyväksyä sisältö.

#### 6) Avoimmuus tiedon tuottajasta ####

Mikäli sisältö on tuotettu tekoälyllä, tulee tämä olla selkeästi ilmaistu. Vastuurajoitteiden esittäminen kuuluu myös tähän yhteyteen. 

#### 7) Sisällön jäljitettävyys ####

Sivuston tulee olla versionhallinnan piirissä, jolloin sivuston sisältö aiemmalla ajanhetkellä voidaan jälkikäteen tarkastaa. Tämä esimerkkisivusto on toteuttu GIT-versionhallinnalla. 

#### 8) Sisällön käytön seuranta ####

Lokituksen avulla tulee seurata sisällön käyttöä.

#### 9) Sisäinen pilotointi ja sisäinen käyttö ####

Ratkaisu tulee toteuttaa sisäisenä pilottana ensin ja ratkaisulla tulee olla pilotoinnin jälkeen myös sisäisiä käyttäjiä, mikä nopeuttaa virheellisen sisällön tunnistamista. 