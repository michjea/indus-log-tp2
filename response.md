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
