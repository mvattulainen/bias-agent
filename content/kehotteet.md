---
title: "Kehotteet"
---


Tapoja käyttää sivustoa tekoälyagentilla:

Esimerkkejä:

1) Agentti käyttää sivustoa luotettuna lähteenä analysoidessaan ulkoista sisältöää

"By using the cognitive biases as identified in https://mvattulainen.github.io/bias-agent site and the source analysis workflow in Ajatteluharhat-skill page on the site, analyse this article: https://www.is.fi/terveys/art-2000012101212.html. As fallback, if you can not access the skill, use the few-show prompting examples of analysis output presented in the Soveltaminen section "

Tämä kehote edellyttää, että tekoälyagentilla on webselauskyvykkyys (web browser) ja että kyvykkyys poimia sisältöä websivuilta (webscraping).

2) Agentti opettaa kognitiivisia harhoja ylläpitäen tietoa lähikehityksen vyöhykkeestä.

"By using the cognitive biases as identified in https://mvattulainen.github.io/bias-agent site and the Opettaja-skill page on the site, run one teaching session with me including 1 cognitive bias. Maintain the learning log on my personal computer. Difficulty level: adult learner. As fallback, if you can not access the skill, use the few-show prompting examples of analysis output presented in the Oppimisloki page."

Tämä kehote edellyttää, että tekoälyagentilla on pääsy tiedostojärjestelmään (file access) ainakin yhden kansion osalta. 

3) Agentti luo esimerkkejä kognitiivista harhoista

"By using the cognitive biases as identified in https://mvattulainen.github.io/bias-agent site and the source analysis workflow in Ajatteluharhat-skill page on the site, generate 3 examples of survivor bias on health study topic. As fallback, if you can not access the skill, use the few-show prompting examples presented in the Harjoituksia section "

Vaaditut edellytykset ovat tässä samat kuin kohdassa 1. 
