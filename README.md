# TP2 Industrialisation du logiciel

## Description

Ce projet est réalisé dans le cadre du TP2 du cours d'industrialisation du logiciel. Il s'agit d'un projet pour tester les outils de CI/CD et de qualité de code.

## Exercice 1

Test de l'image Docker :

```bash
docker pull ghcr.io/michjea/tp2:latest

docker run --rm -p 80:80 ghcr.io/michjea/tp2:latest
```

Ensuite, aller sur http://127.0.0.1:80
