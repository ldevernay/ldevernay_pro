---
title:  "Classement des compagnies d'assurance"
date:   2026-03-20 12:00:00 +0200
excerpt: Analyse des sites d'assurance en fonction de critères liés à l'écoconception et à l'accessibilité
categories: ecoconception rgesn numeriqueresponsable accessibilite
---

Alors que la plupart des assureurs entament leur transition hors des énergies fossiles, quels sont les impacts de leurs sites web ?

Début 2026, suite à un rapport de l’ONG Reclaim Finance, le magazine Vert propose un article sur les assurances-vies afin de distinguer leurs investissements dans les énergies fossiles. 
[https://vert.eco/articles/maif-axa-goodvest-comment-choisir-une-assurance-vie-qui-ne-finance-pas-les-geants-du-petrole](https://vert.eco/articles/maif-axa-goodvest-comment-choisir-une-assurance-vie-qui-ne-finance-pas-les-geants-du-petrole)

L’objectif est de permettre au consommateur de choisir un investissement en accord avec ses propres valeurs. 
En complément de ce classement, j'ai décidé de regarder de plus près les engagements liés au numérique pour les sociétés représentées. Et de tester par la même occasion un nouvel outil de mesure : webNRG.  

## Méthodologie
La méthodologie est plutôt simple (donc forcément imparfaite) : il s’agit de mesurer la page d’accueil du site de chaque compagnie d'assurance pour pouvoir ensuite les comparer.  
Pour cela, c’est l’outil [webNRG](https://website-tester.green-coding.io) proposé par [Green Coding Solutions Gbmh](https://www.green-coding.io/) qui a été retenu.  
Plusieurs raisons à cela : 
* L’outil est gratuit
* Au-delà des données transférées, l’énergie consommée est mesurée via la sollicitation du CPU
* Ça faisait un moment que je voulais le tester et c’est l’occasion d’avoir un échantillon un peu large et de rédiger un article
  
La quantité de données transférées résulte de l’addition de la quantité liée au chargement initial et celle liée au scroll sur la page.  
La quantité d’énergie correspond au seul chargement de la page.  
En complément des métriques, webNRG fournit des scores calculés à partir de celles-ci et évalue les impacts environnementaux. La méthodologie est disponible [ici](https://website-tester.green-coding.io/methodology.html).  
Toutefois, pour la comparaison, j’ai préféré m’en tenir aux métriques.   
Pour en savoir plus sur les limites de la méthodologie retenue, voir plus loin mes retours sur l’outil. 
   
Plusieurs sites (8 sites sur 27) se sont avérés impossibles à mesurer avec WebNRG :  
* [https://www.milleis.fr](https://www.milleis.fr) 
* [https://mon.apicil.com](https://mon.apicil.com) 
* [https://www.swisslife.fr/particuliers.html](https://www.swisslife.fr/particuliers.html)
* [https://www.maaf.fr/fr/assurance](https://www.maaf.fr/fr/assurance)
* [https://www.gmf.fr/](https://www.gmf.fr/)
* [https://www.mma.fr/](https://www.mma.fr/) 
* [https://www.abeille-assurances.fr/](https://www.abeille-assurances.fr/) 
* [https://www.macif.fr/](https://www.macif.fr/) 
  
Ceci semble être lié à un blocage des *workers* Cloudflare par les sites en question (merci au passage à Arne Tarara pour les explications).
  
## Résultats obtenus
Les résultats des mesures ainsi que les liens vers les sites et vers les résultats obtenus avec WebNRG sont disponible dans [un tableur partagé via le kDrive d'Infomaniak](https://kdrive.infomaniak.com/app/share/691604/6f7244eb-1293-4411-a81a-feda51f2ca48).  
Au global, il en ressort qu'il n'y a pas nécessairement de corrélation entre le fait de se désengager des énergies fossiles et le fait de proposer un site moins impactant.

On distingue 5 sites qui se détachent du lot avec des pages d'accueil a priori optimisées (même si des pistes d'amélioration subsistent) :
* Société Générale Assurances
* MAIF
* AXA
* Allianz
* HSBC Assurances
  
A l'exception de HSBC Assurances, ces sites ont déjà entamé des démarches d'amélioration de l'accessibilité.
  
Inversement, deux pages d'accueil se détachent avec des métriques particulièrement élevées, sur lesquelles nous allons nous attarder un peu plus afin de voir comment elles pourraient être améliorées :
* Crédit Agricole Assurances
* Generali

### Crédit Agricole Assurances
![Page d'accueil Crédit Agricole Assurances](/images/articles/ca_assurances_home.jpg)  
  
Concernant cette page d'accueil, certaines actions simples pourraient être mises en place
* Certaines images gagneraient à être optimisées
* Le chargement de certains services tiers pourrait être différé
* Les polices de caractères pourraient être allégées

Plusieurs autres optimisations techniques pourraient être facilement mises en place avec des résultats potentiellement importants. Les travaux actuels en interne sur le sujet laissent présager du meilleur pour la suite.

### Generali
![Page d'accueil Generali](/images/articles/generali_home.jpg)
  
Sur cette page d'accueil :
* Le lancement automatique de vidéos et d'animations vient augmenter l'impact sur le CPU (et les transferts de données).  
* Certaines images ne sont pas optimisées
* Les services-tiers apparaissent très nombreux et impactants

Plusieurs autres optimisations techniques seraient faciles à mettre en place avec des résultats potentiellement importants (cache, etc.).  
  
Certaines dépendances, si elles ne sont pas clairement identifiées, peuvent poser des problèmes de performance voire vis-à-vis du RGPD (par exemple les polices Google).

Pour ce qui est de l'accessibilité, certaines erreurs apparaissent dès l'affichage de la page d'accueil. Le schéma pluriannuel, affiché comme en cours de rédaction, devrait être publié dans les plus brefs délais afin de répondre aux obligations légales.

### Synthèse de mes retours sur WebNRG
Comme mentionné précédemment, j’ai choisi WebNRG pour cet article afin de le tester de façon un peu plus poussée. 

**Points forts :** 
* Récolte de métriques liées au CPU
* Mesure du scroll sur la page plutôt que du seul chargement. 
* Historique conséquent des mesures 
* Possibilité de lancer plusieurs mesures à la suite
* Outil gratuit  
  
**Points faibles :** 
* Il serait intéressant de pouvoir tenir compte des cookies et du cache. Et plus généralement de pouvoir mesurer un parcours utilisateur
* Les résultats ne sont pas toujours simples à déchiffrer quand on commence à creuser
* De nombreux sites sont impossibles à mesurer  
* Comme pour la plupart des outils existants, la projection environnementale est parcellaire, que ce soit en termes de métriques prises en compte ou d'indicateurs calculés. De plus, l'hypothèse est prise d'une localisation en Allemagne, ce qui peut être contraignant.
  
Au final, c’est un outil intéressant mais avec encore quelques axes d’amélioration possibles.

### Accessibilité
L’accessibilité numérique est un sujet essentiel, d’autant plus pour les sites proposant des produits et services liés à la santé. Sur les sites présentés ici, des parcours en ligne permettent souvent d'effectuer une simulation voire de souscrire. Il est donc essentiel que ces démarches soient accessibles à tous.   
  
Les obligations légales sont rappelées ici : [https://accessibilite.numerique.gouv.fr/obligations/](https://accessibilite.numerique.gouv.fr/obligations/)   
Elles peuvent aussi être vérifiées en ligne : 
* [https://rgaa.info/](https://rgaa.info/)
* [https://valentin-hauye.web.app/](https://valentin-hauye.web.app/)   
  
Par exemple, il peut être imposé de :
* Auditer un service numérique sous l’angle du RGAA (Référentiel Général d’Amélioration de l’Accessibilité)
* Rédiger et partager un schéma pluriannuel d’amélioration de l’accessibilité
* Afficher directement sur la page d’accueil l’état de conformité du service numérique
* Proposer un moyen de contact, notamment vers le Défenseur des Droits
  
Dans ces conditions, il va sans dire qu’une surcouche d’accessibilité ne saurait en aucun cas permettre seule de répondre à ces obligations. Voir notamment cet article : [https://design.numerique.gouv.fr/articles/2025-04-03-les-surcouches-ne-rendent-ni-accessible-ni-conforme/](https://design.numerique.gouv.fr/articles/2025-04-03-les-surcouches-ne-rendent-ni-accessible-ni-conforme/)   
Les sites étudiés ici présentent presque tous une page consacrée à l’accessibilité. Toutefois, une bonne partie d’entre eux ne répondent pas à l'ensemble des obligations légales. 

### RGESN
Le [RGESN (Référentiel général de l’écoconception de service numérique)](https://www.arcep.fr/mes-demarches-et-services/entreprises/fiches-pratiques/referentiel-general-ecoconception-services-numeriques.html) est un référentiel de bonnes pratiques d’écoconception permettant de valider et de structurer les actions mises en place au niveau d’un service numérique.   
Sur l'ensemble du classement proposé par Vert, seule la MAIF affiche une déclaration RGESN sur son site institutionnel. Pour autant, d'autres ont déjà lancé en interne des démarches liées à ce référentiel. Le RGESN apparaît ici comme un facteur différenciant (mise en avant de ceux qui se plient à cet exercice) mais pourrait, à terme, devenir un facteur discriminant.  
En tant que tel, il n’est pour l’instant pas obligatoire de l’appliquer. Pour en savoir plus à ce sujet et consulter des exemples : [https://www.laudevsat.fr/articles/liste_rgesn/](https://www.laudevsat.fr/articles/liste_rgesn/)   
Il s'agit selon moi d'un outil important pour lancer et structurer une démarche d'écoconception de services numériques. 

## Conclusion
L'écoconception et l'accessibilité ne sont pas forcément directement corrélées à un désengagement des énergies fossiles.  
  
Le sujet de l'accessibilité a été identifié par la grande majorité des acteurs recensés, notamment via l'adoption des obligations légales. Malgré tout, pour certains, le sujet n'apparaît pas encore sur les pages d'accueil.  
  
Du point de vue des métriques liées à l'écoconception, les résultats sont satisfaisant pour la plupart des sites, probablement grâce à des optimisations de performance. Le RGESN est plutôt le grand absent pour la quasi-totalité des pages analysées, ce qui est regrettable. Il faut toutefois garder en tête qu'il n'exite à ce jour pas d'obligations légales. Le référentiel sera sûrement un passage obligatoire pour amorcer ou consolider les démarches d'écoconception. 


> 👉 Vous pouvez [**me contacter**](/contact/) pour que je vous accompagne sur ces sujets, notamment pour un audit d'écoconception et en particulier articulé autour du RGESN. Quelques petites actions peuvent souvent être mises en oeuvre rapidement et ce premier pas permet d'enclencher la démarche d'amélioration continue. 



