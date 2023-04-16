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

# Exercice 1

## b)

**Quelles étapes (steps) sont réalisées par cette action ?**

Les étapes sont les suivantes :

    Checkout : permet de récupérer le code source du dépôt GitHub sur lequel le workflow est configuré.
    Set up Python 3.10 : permet d'installer la version 3.10 de Python.
    Install dependencies : installe les dépendances Python, à savoir flake8 et pytest, ainsi que toutes les dépendances définies dans le fichier requirements.txt.
    Lint with flake8 : exécute flake8 pour vérifier la syntaxe et la qualité du code.
    Test with pytest : exécute pytest pour lancer les tests.

**Une étape est définie au minimum par 2 éléments, lesquels sont-ils et à quoi servent-ils ?**

Chaque étape est définie par deux éléments :

    un nom (name) qui permet de donner un nom à l'étape pour la rendre plus explicite.
    une action (run ou uses) qui permet de définir ce qui doit être exécuté.

**La première étape contient le mot-clé ‘with’, a quoi sert-il ?**

La première étape contient le mot-clé 'with' pour permettre de spécifier des options supplémentaires pour l'action "uses". Dans ce cas, l'option spécifiée est la version de Python à utiliser.

## Exercice 2

## a)

**Sur l'onglet Summary d'une analyse de code, SonarCloud fournit 4 indicateurs. Quels sont-ils et quelles sont leurs utilités ?**

- Bugs : il s'agit du nombre de bugs détectés dans le code analysé. Les bugs sont des erreurs de programmation qui peuvent entraîner des comportements inattendus ou des plantages du logiciel.

- Vulnerabilities (vulnérabilités) : il s'agit du nombre de vulnérabilités détectées dans le code analysé. Les vulnérabilités sont des faiblesses dans le code qui peuvent être exploitées par des attaquants pour compromettre la sécurité du système.

- Code Smells (odeurs de code) : il s'agit du nombre de violations des bonnes pratiques de programmation détectées dans le code analysé. Les odeurs de code peuvent rendre le code plus difficile à maintenir, à comprendre et à modifier.

- Security Hotspots (points chauds de sécurité) : il s'agit du nombre de points chauds de sécurité détectés dans le code analysé. Les points chauds de sécurité sont des zones du code qui nécessitent une attention particulière en raison de leur sensibilité aux attaques.

**À quoi sert l'indicateur Quality Gate ?**

L'indicateur Quality Gate de SonarCloud permet de définir des seuils de qualité pour le code analysé Il permet de s'assurer que le code respecte un ensemble de critères définis et de fournir un retour d'information immédiat sur la qualité du code. Si le code ne répond pas aux critères définis, il ne passera pas le Quality Gate et une alerte sera générée.

## b)

**Quelle est la différence entre les sections New code et Overall Code dans l'onglet Summary ?**

La section "New code" de l'onglet Summary de SonarCloud représente les résultats de l'analyse du code qui a été ajouté ou modifié depuis la dernière analyse, tandis que la section "Overall Code" représente les résultats pour l'ensemble du code. La section "New code" peut aider à identifier rapidement les problèmes dans le code récemment ajouté ou modifié.

**Y a-t-il des Code Smells ? Si oui, combien et pour quelles raisons ?**

Oui, il y a 3 "Code Smells", pour wallet.py :

- Remove the unused function parameter "deferred".
- Update this function so that its implementation is not identical to spend_cash on line 20.
- Remove the unused function parameter "deferred".

**Y a-t-il des Security Hotspots ? Si oui, combien et pour quelles raisons ?**

Oui, il y a 1 "Security Hotspot".

- The python image runs with root as the default user. Make sure it is safe here.
