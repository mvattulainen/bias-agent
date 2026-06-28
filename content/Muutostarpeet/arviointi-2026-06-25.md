---
title: "Arviointi"
---

**Arvioidut tiedostot:** 66
**Rajatut kansiot:** `Soveltaminen`, `Muutostarpeet`
**Luotu:** 2026-06-25

## Tiivistelmä

Wiki on rakenteeltaan melko yhtenäinen: 64 ajatusvirhesivua löytyvät indeksistä, kategoriat vastaavat sivujen metatietoja, `INFO: [[sivustosta|Sivustosta]].` on tallella ja `Sukulaisajatusvirheet`-osioiden sisäiset wikilinkit käyttävät nyt suomenkielisiä näyttönimiä. Selkeimmät korjattavat asiat ovat yksi rikkinäinen `Soveltaminen`-linkki indeksissä, 43 linkittämätöntä englanninkielistä sukulaiskäsitettä, yhden sivun tyhjä englanninkielinen nimi sekä muutama käsitteellinen rajapinta, jota kannattaisi tarkentaa.

## Havainnot

| # | Kohde | Ongelmatyyppi | Havainto | Ehdotettu korjaus | Vakavuus |
|---:|---|---|---|---|---|
| 1 | [[Index|Index]] | Rikkinäinen linkki | `Soveltaminen`-osiossa on linkki raporttiin `2026-06-02-iltalehti-taalla-punkkeja-on-nyt-eniten`, mutta vastaavaa tiedostoa ei löydy nykyisestä `Soveltaminen`-kansiosta. | Poista linkki tai palauta puuttuva raporttikansio ja raporttitiedosto. | Korkea |
| 2 | Useat ajatusvirhesivut | Epäyhtenäinen linkitys | `Sukulaisajatusvirheet`-osioissa on 43 linkittämätöntä englanninkielistä käsitettä, kuten `Planning fallacy`, `Confirmation bias`, `Status quo bias`, `Selection bias` ja `Representativeness heuristic`. | Päätä, ovatko nämä vain ulkoisia käsitteitä vai paikallisia käsitteitä. Linkitä paikallisiin vastineisiin tai lisää suomenkielinen selite sulkuihin. | Keskitaso |
| 3 | [[12-it-gets-worse-before-it-gets-better-trap|12 ‘Ensin pahenee’ -ansa]] | Metatieto | Sivun `englanniksi`-kenttä on tyhjä, vaikka muilla ajatusvirhesivuilla kenttä sisältää englanninkielisen nimen. Tämä rikkoo otsikko- ja aliasrakenteen yhtenäisyyttä. | Lisää englanninkielinen nimi tai dokumentoi, että tällä sivulla englanninkielistä vastinetta ei käytetä. | Keskitaso |
| 4 | [[Index|Index]] | Rakenne | Viimeisen kategoriakohdan ja `## Soveltaminen` -otsikon väliltä puuttuu tyhjä rivi. Tämä ei välttämättä riko Obsidiania, mutta heikentää Markdown-rakenteen luettavuutta. | Lisää tyhjä rivi ennen `## Soveltaminen`. | Matala |
| 5 | [[03-overconfidence-effect|03 Ylivarmuusvaikutus]], [[41-forecast-illusion|41 Ennusteilluusio]], [[58-overoptimism|58 Yltiöoptimismi]] | Käsitteellinen rajaus | Sivut ovat hyödyllisiä erillisinä, mutta rajapinta on tiivis: kaikki käsittelevät liian varmaa tai myönteistä arviota tulevasta. | Lisää kullekin sivulle lyhyt erottelulause: ylivarmuus koskee kalibrointia, ennusteilluusio ennusteiden arvostamista ja yltiöoptimismi myönteistä vinoumaa. | Keskitaso |
| 6 | [[38-false-causality|38 Väärä kausaliteetti]], [[49-association-bias|49 Assosiaatioharha]], [[13-story-bias|13 Tarinaharha]] | Päällekkäisyys | Sivuilla on luonnollista päällekkäisyyttä, mutta lukija voi sekoittaa yhteisesiintymän, tarinallisen selityksen ja varsinaisen kausaaliväitteen. | Lisää rajatapauksia vertaava esimerkki: sama havainto voidaan tulkita assosiaationa, tarinana tai vääränä kausaalisuutena riippuen väitteen voimakkuudesta. | Keskitaso |
| 7 | [[44-action-bias|44 Toimintaharha]], [[45-omission-bias|45 Laiminlyöntiharha]], [[27-zero-risk-bias|27 Nollariskiharha]], [[33-loss-aversion|33 Tappionkarttaminen]] | Rajatapaukset | Päätöksenteko- ja riskisivuilla on läheisiä mekanismeja. Etenkin terveysaiheisissa sovelluksissa toiminta, toimimatta jättäminen, nollariskin tavoittelu ja tappion välttely voivat esiintyä yhdessä. | Lisää ristiinlinkitetty vertailu tai pieni päätöspuu siitä, mikä harha on ensisijainen eri tilanteissa. | Keskitaso |
| 8 | Useat ajatusvirhesivut | Rakenne | Ajatusvirhesivuilla on sekä ylä- että alanavigaatio sekä kaksinkertaiselta näyttävä erotinrakenne ennen alanavigaatiota. Tämä voi olla tarkoituksellinen, mutta se tekee sivuista raskaita ja voi tuottaa ylimääräistä toistoa julkaisussa. | Päätä, tarvitaanko alanavigaatiota enää, jos Quartz tai Obsidian näyttää navigaatiota muualla. | Matala |
| 9 | [[Index|Index]] | Näyttönimet | Indeksin ajatusvirhelinkit näyttävät usein suomenkielisen nimen ja englanninkielisen nimen sulkeissa, kun taas `Sukulaisajatusvirheet` käyttää nyt vain suomenkielisiä näyttönimiä. | Tee linjaus: indeksissä voidaan säilyttää kaksikieliset nimet, mutta lähisuhdelistoissa käytetään vain suomea. Kirjaa tämä käytännöksi. | Matala |
| 10 | [[llm-wiki|LLM-wiki]] | Selkeys | Sivuston prosessikuvaus kertoo, ettei malli automaattisesti päivitä käsitteitä, mutta nykyinen työnkulku tuottaa `Muutostarpeet`-raportteja, jotka ohjaavat päivityksiä. | Päivitä kuvausta niin, että se erottaa automaattisen analyysin, muutostarpeiden tunnistamisen ja ihmisen hyväksymän käsitemuutoksen. | Matala |

## Ristiriidat ja päällekkäisyydet

Selviä suoria ristiriitoja määritelmien välillä ei löytynyt. Merkittävimmät päällekkäisyydet ovat odotettuja ja liittyvät käsitteisiin, jotka kuuluvat samaan päätöksenteon tai syy-seurauspäättelyn alueeseen. Niissä hyödyllisin parannus ei ole sivujen yhdistäminen vaan rajatapauksien lisääminen.

Tärkeimmät rajapinnat ovat:

- [[03-overconfidence-effect|03 Ylivarmuusvaikutus]] / [[41-forecast-illusion|41 Ennusteilluusio]] / [[58-overoptimism|58 Yltiöoptimismi]]
- [[38-false-causality|38 Väärä kausaliteetti]] / [[49-association-bias|49 Assosiaatioharha]] / [[13-story-bias|13 Tarinaharha]]
- [[44-action-bias|44 Toimintaharha]] / [[45-omission-bias|45 Laiminlyöntiharha]] / [[27-zero-risk-bias|27 Nollariskiharha]]

## Huomiot ja rajaukset

- Tämä on arviointiraportti; wikin sisältösivuja ei muutettu.
- `Soveltaminen`- ja `Muutostarpeet`-kansiot rajattiin pois arvioinnista.
- Havainnot tarvitsevat ihmisen tarkistuksen ennen toteuttamista.
