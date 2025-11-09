Fonds Macro Global – Mémorandum interne

À : Analyste quantitatif junior
De : Directeur de la stratégie quantitative
Date : 5 septembre 2025
Objet : Mandat de projet : Révision de notre modèle de risque de corrélation internationale

1. Problématique et mandat

Bonjour,
Je vous confie un projet qui touche au cœur de notre cadre de gestion des risques. Comme vous le savez,

la performance de notre fonds durant les récentes périodes de tensions sur les marchés—notamment le choc de
la COVID-19 en 2020 et les turbulences inflationnistes de 2022—a été considérablement entravée par l’échec
de nos stratégies de diversification internationale. Une analyse post-mortem a révélé que nos modèles de VaR
(valeur à risque) ont été violés à un niveau sans précédent. Le principal responsable était une incompréhension
fondamentale de la dynamique des corrélations ; les avantages historiques de la détention d’actifs non corrélés
ont disparu bien plus rapidement et complètement que nos modèles ne l’avaient prédit, nous exposant à un
risque imprévu. Notre examen préliminaire suggère que nos modèles existants sont en cause. Ils reposent
sur deux piliers trop simplistes : un modèle autorégressif (AR) de base pour la prévision à court terme et un
modèle linéaire simple pour expliquer la relation entre la corrélation et la peur du marché. Les deux se sont
avérés inadéquats.

Votre tâche est de mener une analyse diagnostique complète et de proposer un nouveau cadre plus robuste
pour la modélisation et la prévision de cette dynamique des corrélations. Afin de garantir que notre analyse soit
exhaustive et représentative de notre empreinte mondiale, vous ne vous concentrerez pas sur un seul marché.
Vous sélectionnerez plutôt un portefeuille de cinq indices boursiers internationaux à analyser (par ex., le DAX
allemand, le Nikkei 225 japonais, le Bovespa brésilien, le Nifty 50 indien, etc.). Votre portefeuille choisi
doit inclure au moins deux marchés développés et deux marchés en développement/émergents. Le choix du
cinquième marché est à votre discrétion. Votre analyse portera sur la corrélation entre chacun de ces cinq
indices de marché et le marché américain (représenté par le S&P 500). Cette analyse constituera la base d’une
nouvelle ≪ vision interne ≫ sur le risque de corrélation, et votre rapport sera présenté directement au comité
de risque. Le livrable final de ce projet sera un rapport de recherche complet, adapté à cette présentation, qui
décrira votre méthodologie, vos résultats empiriques et vos recommandations concrètes. Les sections suivantes
décrivent un plan de recherche proposé pour guider votre travail.

2. Plan de recherche proposé

2.1. Caractérisation de la variable dépendante

Avant de pouvoir modéliser ou prévoir quoi que ce soit, nous avons besoin d’une compréhension approfondie
des variables en question. Votre première étape consiste à construire nos indicateurs de risque clés. Vous
calculerez la corrélation mobile sur 6 mois (126 jours) entre le S&P 500 (notre proxy américain) et chacun des
cinq indices de marchés internationaux que vous avez sélectionnés, en utilisant des données quotidiennes de
2010 à aujourd’hui. Nous utilisons une fenêtre de 126 jours, car c’est une pratique courante dans l’industrie
pour capturer la dynamique du risque à moyen terme, qui est sensible à l’évolution des conditions de marché
sans être excessivement bruyante. Ce processus aboutira à cinq séries de corrélation distinctes pour votre

1



analyse. Une fois construites, une analyse préliminaire approfondie des cinq séries est essentielle. Je suis
particulièrement préoccupé par leurs propriétés de séries temporelles. Une question essentielle à laquelle nous
devons répondre est de savoir si ces séries de corrélation sont stationnaires. Ce n’est pas une simple curiosité
statistique ; la réponse a de profondes implications sur l’ensemble de notre stratégie de modélisation. Veuillez
effectuer les tests formels appropriés (par ex., Dickey-Fuller Augmenté) pour chacune de vos cinq séries de
corrélation. J’attends de vous que vous discutiez de la signification économique de vos résultats. Trouvez-vous
des résultats cohérents entre tous les marchés, ou y a-t-il des différences entre vos séries de marchés développés
et émergents ? L’intégration des marchés mondiaux semble-t-elle revenir à une moyenne stable de long terme,
ou les chocs sont-ils persistants ? Votre analyse visuelle et vos statistiques descriptives de la première étape
devront être utilisées pour fournir un contexte crucial à votre interprétation de ces tests formels.

2.2. Évaluation de notre approche de prévision existante

Une fois que vous maı̂trisez les propriétés des séries, je dois évaluer notre méthodologie de prévision actuelle.
Veuillez construire un modèle autorégressif (AR) simple pour prévoir la série de corrélations un pas en avant
(one-step-ahead) pour chacun de vos cinq marchés. Cette approche nous a bien servis dans des marchés stables,
mais s’est avérée fragile ; votre analyse devra quantifier à quel point elle est fragile. Votre travail de diagnostic
de la section précédente sera ici primordial. Compte tenu de vos conclusions sur la stationnarité, vous devrez
justifier votre choix de modélisation pour chaque marché : devez-vous modéliser la corrélation dans sa forme
originale (en niveaux), ou est-il plus approprié de modéliser ses variations (en différences) ? Je m’attends à
ce que vous développiez et évaluiez les deux approches. Veuillez présenter les résultats d’estimation de vos
modèles AR(p) choisis dans un tableau récapitulatif professionnel, en rapportant clairement les coefficients et
les erreurs-types. Pour évaluer leur performance, comparez la précision de leurs prévisions hors échantillon
à l’aide d’une métrique standard telle que l’erreur quadratique moyenne (RMSE). De manière critique, votre
rapport doit également inclure des graphiques de séries temporelles qui visualisent vos prévisions par rapport
aux données de corrélation réelles, assortis d’intervalles de confiance à 95 %. Ces graphiques sont essentiels
pour communiquer la fiabilité (ou le manque de fiabilité) du modèle au comité de risque. Bien que vous puissiez
utiliser des méthodes analytiques standard pour générer ces intervalles, votre discussion devrait aborder leurs
limites (par ex., l’hypothèse de normalité des résidus) et mentionner quand une méthode plus robuste, telle
que le bootstrap (ré-échantillonnage), serait appropriée. Enfin, fournissez une recommandation claire sur la
méthode (niveaux vs différences) qui est empiriquement et théoriquement supérieure pour chaque marché.
Cela servira de point de référence par rapport auquel nous jugerons tout nouveau modèle.

2.3. Développement d’un cadre explicatif plus riche

Parallèlement à la prévision, nous devons également comprendre ce qui influence la corrélation. Un modèle
purement autorégressif, bien qu’utile, est une ≪ boı̂te noire ≫ qui nous donne peu d’intuition économique. Pour
gérer le risque, nous devons également comprendre les facteurs économiques sous-jacents de la corrélation.

Notre modèle explicatif existant est, franchement, trop simpliste. C’est une régression linéaire de base qui
modélise la corrélation comme une simple fonction linéaire de la peur du marché, représentée par log(VIX).
La piètre performance de ce modèle en 2020 suggère fortement que cette hypothèse linéaire est erronée.
L’équipe quantitative a une hypothèse de travail selon laquelle la véritable relation est non linéaire et convexe.
Nous pensons qu’à mesure que la peur augmente, la corrélation pourrait non seulement augmenter, mais
augmenter à un rythme accéléré. Cela créerait une dynamique de ≪ point de bascule ≫ qui expliquerait
pourquoi nos modèles linéaires ont échoué de manière si spectaculaire. Votre prochaine tâche consiste à tester
rigoureusement cette hypothèse.

Je m’attends à ce que vous construisiez, estimiez et présentiez les résultats de deux modèles explicatifs
concurrents pour chacun de vos cinq marchés :

1. Notre modèle linéaire existant : Ce modèle inclut uniquement log(VIX) comme régresseur.

Corrt = β0 + β1 log(V IXt) + ϵt

2. Le modèle quadratique proposé : Ce modèle teste l’hypothèse du ≪ point de bascule ≫ en ajoutant un
terme quadratique.

Corrt = β0 + β1 log(V IXt) + β2(log(V IXt))^2 + ϵt



2



Votre rapport doit inclure des tableaux d’estimation professionnels pour les deux modèles (pour les cinq
marchés) afin que nous puissions comparer directement leurs coefficients, leurs erreurs-types et leurs statistiques
d’adéquation (comme le R^2). Je suppose que vous avez déjà inclus le log(VIX) dans votre tableau principal
de statistiques descriptives de la partie 2.1, car c’est une variable clé dans cette analyse. Votre analyse de ces
tableaux devrait déterminer si le cadre non linéaire offre une explication significativement meilleure. Le terme
quadratique β2 est-il statistiquement significatif ? Si oui, que signifient les signes des coefficients β1 et β2 ?
Nous sommes particulièrement intéressés à savoir si les données soutiennent une relation en forme de U (c’est-
à-dire β1 < 0 et β2 > 0), ce qui confirmerait un point de bascule du VIX statistiquement identifiable. Si vous
trouvez une telle relation pour l’un de vos marchés, je veux que vous calculiez le niveau du VIX à ce point de
bascule et que vous discutiez de sa profonde signification économique pour notre stratégie de diversification.
Enfin, un graphique des valeurs ajustées des deux modèles par rapport à la série de corrélation réelle serait un
moyen puissant de visualiser l’amélioration de l’ajustement.

2.4. Synthèse pour un modèle de pointe

L’étape analytique finale consiste à faire la synthèse de ces perspectives. Notre modèle idéal ne devrait pas
seulement expliquer mais aussi prévoir avec précision la corrélation en exploitant les forces des approches de
séries temporelles et explicatives. Je vous suggère de développer et de tester un nouveau modèle de prévision
basé sur un cadre ARX. Ce modèle devrait incorporer à la fois les retards autorégressifs (de votre travail dans
la partie 2.2) et, éventuellement, les termes non linéaires du VIX (de votre investigation dans la partie 2.3).
Assurez-vous que votre modèle est un véritable outil de prévision en utilisant uniquement des informations
décalées (lagged) pour les termes du VIX. Un modèle qui utilise le VIX contemporain pour ≪ prévoir ≫ la
corrélation contemporaine est un modèle explicatif, et non prédictif. Ce sera notre candidat pour le nouveau
modèle de production, donc sa performance de prévision doit être rigoureusement comparée aux modèles AR
plus simples que vous avez développés précédemment.

2.5. Implications stratégiques pour la gestion de portefeuille et des risques

Enfin, la partie la plus critique de votre analyse est de relier vos résultats économétriques à nos décisions
d’affaires réelles. Cette section finale ne nécessite aucun nouveau calcul ; c’est une discussion sur le ≪ et alors
? ≫ pour notre fonds. Votre travail aura presque certainement démontré que nos modèles existants sont de
piètres estimateurs de la corrélation. Dans votre discussion finale, je veux que vous abordiez les conséquences
en aval de cette erreur d’estimation. Pensez à la construction de nos portefeuilles de base. Qu’advient-il de
nos modèles d’optimisation moyenne-variance si les corrélations en entrée sont systématiquement erronées ?
Comment la ≪ frontière efficiente ≫ se comporte-t-elle si elle est construite sur un modèle linéaire, alors que
le monde réel suit une dynamique de ≪ point de bascule ≫ ? Plus précisément, discutez de l’impact sur la
gestion des risques. Comment une mauvaise estimation et prévision de la corrélation affecte-t-elle la fiabilité
des modèles de Valeur à Risque (VaR) et de Perte Attendue (ES) de notre portefeuille ? Si nos modèles ne
parviennent pas à capturer la véritable accélération non linéaire des corrélations lors d’une panique, quelle est
la conséquence pratique pour nos dépassements de VaR et notre capital à risque ?

3. Le livrable final

Veuillez consolider l’ensemble de votre analyse en un seul rapport de recherche professionnel. Le rapport
doit être structuré de manière logique, reflétant le déroulement d’un article de recherche formel :

• Introduction : Décrivez brièvement la problématique d’affaires, l’inadéquation des anciens modèles et
l’objectif de votre recherche.

• Données et méthodologie : Décrivez vos données et justifiez clairement tous vos choix méthodologiques
(par ex., fenêtre de corrélation, tests de stationnarité, critères de sélection de modèle, métriques d’évaluation
des prévisions).



3



• Résultats empiriques : Présentez vos résultats de manière claire et organisée. Utilisez des tableaux
et graphiques professionnels pour appuyer votre analyse de la stationnarité, la performance des divers
modèles de prévision et les preuves d’une relation non linéaire avec le VIX.

• Conclusion et recommandations : Concluez avec un résumé de vos principaux résultats et fournissez
des recommandations claires et concrètes pour le comité de risque. Quel est le modèle de prévision le
plus précis et qu’implique le cadre du ≪ point de bascule ≫ pour nos stratégies d’allocation d’actifs et de
couverture ?

Le livrable pour cette étude de cas est un court article. Votre article doit fournir des discussions sur les
questions dans un document ne dépassant pas 5 pages (excluant les graphiques, les tableaux et les références),
à simple interligne, avec la police Times New Roman de 12 points et des marges de 1 pouce. Vous devez
également fournir (séparément) votre script/code pour votre analyse. L’accent pour cet exercice est mis sur votre
compréhension des statistiques et de leurs applications et non sur votre capacité à écrire du code. En tant que
tel, la note sera principalement composée de votre synthèse du cas plutôt que de votre capacité à écrire le code
nécessaire pour répondre aux questions. Supposez que la personne qui lit votre rapport a une compréhension
de base des statistiques et de la finance. Cela implique que vous devriez consacrer suffisamment d’espace à la
discussion des concepts plus complexes dans le contexte de ce cas. Si, pour une raison quelconque, vous n’êtes
pas en mesure d’écrire le code nécessaire pour répondre à certaines ou à toutes les questions, vous pouvez
fournir des explications sur la manière dont vous auriez répondu à la question si vous aviez été capable d’écrire
le code. Faire cela me permettra de vous donner une note partielle. La clarté de votre rédaction et la justification
de vos décisions économétriques sont tout aussi importantes que les résultats eux-mêmes. J’ai bien hâte de lire
votre rapport.



4
