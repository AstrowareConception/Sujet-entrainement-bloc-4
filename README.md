# AquaVigie — Sujet d'entraînement Bloc 4

**Expert en ingénierie du logiciel · RNCP35419 · C14 à C18 · sujet non officiel.**

Ce dépôt rassemble **les supports de conception** du cas fictif AquaVigie, régie intercommunale d'eau potable. **Aucun projet de code applicatif ni déploiement Docker n'est demandé dans cette épreuve.**

## À réaliser

À partir du monolithe Angular + Spring Boot + PostgreSQL décrit dans `SUJET.md` et du diagramme de départ `architecture/existant.drawio`, produire cinq PDF distincts et leurs sources de diagrammes `.drawio` :

1. analyse de l'existant et justification du découplage ;
2. veille IA, choix de modèle et démarche d'entraînement/validation ;
3. architecture distribuée argumentée, stockage, protocoles et pseudocode ;
4. migration progressive, réversibilité et cinq règles d'or ;
5. tests, non-régression, observabilité, robustesse et qualité ML.

Le dossier final doit être livré en **une archive ZIP**, pas dans un dépôt de code obligatoire. Ce dépôt n'est qu'une **annexe de travail** : il propose un diagramme draw.io de l'existant, des exemples de données fictives et un gabarit de livrables **non corrigés**.

## Point de vigilance

- Des capteurs peuvent transmettre en retard ou en double.
- La colonne `incidentWithin6h` est une **étiquette créée a posteriori** : ne jamais l'utiliser comme variable explicative à l'inférence.
- Les fonctions de gestion critiques doivent continuer à fonctionner en cas d'indisponibilité du modèle.
- Les objectifs de performance et de volumétrie sont **des hypothèses pédagogiques**, pas des chiffres de production.

Consultez `SUJET.md` et `donnees/README.md` avant de commencer.

Ce matériel d'entraînement est **non officiel** et distinct des sujets du certificateur.