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

# Exercice 3

## a)

**1. Que fait le job pytest ?**

Le job pytest exécute des tests unitaires avec pytest. Il installe les dépendances du projet, crée un environnement virtuel, exécute les tests unitaires et vérifie que tous les tests passent.

**2. Que fait le job image-creation ?**

Le job image-creation crée une image Docker à partir du fichier Dockerfile du projet en utilisant kaniko, une alternative à Docker. Cette image est ensuite stockée dans le registre Docker de GitLab.

**3. Que fait le job package-creation ?**

Le job package-creation crée un package Python sous forme de fichier .whl à partir du code source du projet. Il utilise le module build pour créer le package et le module twine pour le publier sur le registre PyPI.

**4. Les jobs s'exécutent-ils dans le même ordreque défini dans le fichier ? Sinon, pourquoi ?**

Les jobs ne s'exécutent pas toujours dans le même ordre que défini dans le fichier .gitlab-ci.yml. GitLab exécute les jobs dans l'ordre déterminé par leur dépendance, qui peut être définie en utilisant les mots clés only/except et les variables d'environnement. Par exemple, un job ne sera exécuté que si le job précédent a réussi.

**5. Le stage 2 génère une image Docker. Où est-elle stockée et comment pouvez-vous la retrouver ?**

L'image Docker créée par le stage 2 est stockée dans le registre Docker de GitLab, qui peut être consulté dans l'onglet "Packages & Registries" de GitLab. Il peut également être récupéré en utilisant la commande Docker pull en spécifiant l'emplacement de l'image dans le registre Docker de GitLab.

**6. Le stage 3 génère un wheel Python. Où est-il stocké et comment pouvez-vous le retrouver ?**

Le wheel Python créé par le stage 3 est stocké dans le dossier dist/ du projet. Il est également publié sur le registre PyPI à l'aide du module twine, comme spécifié dans le fichier .gitlab-ci.yml. Le package peut être téléchargé depuis le registre PyPI ou en utilisant la commande pip install en spécifiant le nom du package et le dépôt PyPI.
