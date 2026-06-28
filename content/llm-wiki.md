---
title: "LLM-wiki"
---


Tämä koneellisesti tuotettu sivusto on esimerkki LLM-wikistä.

LLM-wiki-ideasta voi lukea tarkemmin täältä (englanti): [Karpathy LLM-wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)

LLM-wikin keskeisiä hyötyjä ovat:
- Asiantuntijan valitsemat luotettavat lähteet yleisen kielimallin yleisen tiedon sijaan
- Suurestä määrästä/ laajoista lähteistä voidaan tiivistää keskeinen sisältö 
- Tekoälyagentti voi muodostaa vastauksen wikin tietojen perusteella ja vastaus itsessään takaisin syötettynä kehittää wikin sisältöjä
- Wikin voi rakentaa siten, että sekä wikin sisältö että agentin käyttämä kielimalli ovat paikallisella tietokoneella

LLM-wikin haittoja ovat:
- Wikin sisällöt ovat agentin tuottamia, jolloin lähteiden sisällöt saattavat sisältää hallusinaatioida 
- Toisin kuin RAG (retrieval augmentit generation) wiki ei yleensä tuota/käytä sanatarkkoja lainauksia lähdeteksteistä

Näin wiki toimii:

Wiki ja koko sivusto luodaan [[Sivusto-skill|Sivusto-skill]] taidolla, jonka laajaa kielimallia toteuttaa.  

```mermaid  
flowchart TD  
A[Lähteet] 
B[Käsitteet]
C[Soveltaminen]
D[Muutostarpeet]
E[Oppiminen]
F[Sisällön arviointi]
A --> B
B --> C
C --> D
D --> B
B --> E
B --> F
F --> D
E -..-> D
```

Sivuston lähteinä ovat Dobellin (julkisista lähteistä rekonstruoituna)  ja Mungerin ("The Psychology of Human Misjudgment" essee) tunnistamat ajatteluharhat, joista agentti on tunnistanut keskeiset käsitteet. 

Toteutuksessa lähteitä voi vapaasti lisätä kansioon, ja tämän jälkeen agentti päivittää sivuston sisällön automaattisesti. 

Käsitteiden soveltamisesimerkkeinä käytetään Iltalehden ja Iltasanomien valikoituja terveysaiheisia uutisia. Soveltamisessa agentti analysoi artikkelin sivuston käsitteiden avulla ja tuottaa analyysin. Analyysit ovat löytyvät osiosta [[soveltaminen-koonti|Soveltaminen]]

Sisällön arvioinnissa agentti käy läpi käsitteet ja tunnistaa ongelmia, ristiriitaisuuksia ja muita puutteita. 

Sovellusesimerkkien ja sisällön arvioinnin perusteella tunnistetaan [[muutostarpeet-koonti|Muutostarpeet]], joiden toteuttaminen kehittää käsitteitä. 

Kokonaisuuteen kuuluu myös Oppiminen, jossa agentti käy vuoropuhelua käyttäjän kanssa ja  samalla ylläpitäen tietoa käyttäjän lähikehityksen vyöhykeestä eli mitä käyttäjä jo osaa soveltaa, mitä ei ja mikä olisi seuraava opittava asia tarkalleen ottaen. Näin tarkasti ottaen: [[Opettaja-skill|Opettaja-skill]] . Esimerkki oppimislokista näkyy täällä [[oppimisloki|Oppimisloki]]. Tässä esimerkissä oppilas on 5:llä luokalla

Oppimisesta muutostarpeisiin toiminnallisuutta (katkoviiva yllä kuvassa) ei ole vielä toteutettu (28.6.2026). 



