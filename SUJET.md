# AquaVigie — épreuve de conception, bloc 4

**Sujet d'entraînement non officiel · RNCP35419 · C14 à C18.**

## Scénario

AquaVigie surveille un réseau intercommunal d'eau potable. L'application actuelle réunit gestion des zones, télémétrie des capteurs (pression/débit), alertes, interventions et rapports dans un monolithe Java Spring Boot, avec Angular en frontal et PostgreSQL comme base unique. Les pics d'écriture et de calcul dégradent les écrans métiers, alors que la direction souhaite prédire les incidents hydrauliques dans les six heures.

En tant qu'architecte logiciel, vous préparez un **dossier de conception** destiné à une équipe qui reprendra cette solution. Aucun code applicatif n'est fourni ni exigé. Une substitution intégrale par un SaaS du marché ne répond pas à la mission.

## Situation initiale

- Monolithe : gestion des zones, collecteur IoT, alertes, rapports et interventions sur le même déploiement.
- Les utilisateurs consultent Angular et l'API, les équipements transmettent des relevés via une passerelle.
- Même base PostgreSQL pour données transactionnelles, télémétrie et rapports.
- Écritures massives concurrentes des consultations ; services impossibles à redimensionner isolément.
- Pas de chaîne ML indépendante, peu de contrats entre composants et métriques insuffisantes.
- Voir `architecture/existant.drawio` et `annexes/exigences.md`.

## Travail demandé : cinq documents PDF

### 1 — Analyse de l'existant

Décrire les flux actuels ; identifier au moins quatre limites, leurs impacts métiers et les attributs de qualité touchés (performance, sécurité, disponibilité, résilience, maintenabilité). Justifier le découplage entre gestion métier, acquisition de mesures, alertes et fonctions prédictives.

### 2 — Veille et intégration de l'IA

Comparer **deux approches d'intégration** du ML, dont leurs coûts, contraintes opérationnelles et performances. Comparer au moins un modèle classique et une famille de réseaux de neurones ; choisir la variable cible, les entrées réellement disponibles, les fenêtres de temps, la validation chronologique, la stratégie d'entraînement, l'inférence, l'observabilité du modèle et la prévention des fuites de données.

### 3 — Architecture cible

Produire un **diagramme de composants draw.io** montrant acteurs, frontend, points d'entrée, sécurité, responsabilités, acquisition, alertes, prédiction et stockages ; détailler le flux complet d'une mesure jusqu'à une alerte. Justifier les choix SQL/NoSQL/stockage spécialisé ; protocoles synchrones et asynchrones ; gestion des doublons, des retards et des incidents. Décrire un algorithme de validation, déduplication ou agrégation sous forme de pseudocode justifié.

### 4 — Migration et pratiques

Définir une migration progressive, coexistence, synchronisation, conditions de bascule, supervision et **retour arrière** sans interrompre les fonctions critiques. Expliquer l'évolutivité et la reprise par des tiers. Formuler **exactement cinq règles d'or** avec pour chacune principe, risque évité et contrôle vérifiable. Mentionner les documents nécessaires : ADR, contrats API, exploitation, sécurité.

### 5 — Tests et robustesse

Proposer un plan de tests unitaires, intégration, contrat, non-régression, charge, performance et résilience ; définir des scénarios mesurables et leurs métriques, les reprises après panne et l'observabilité. Préciser comment évaluer et surveiller le modèle ML (précision, rappel, taux de fausses alertes, dérive, comportement en cas d'indisponibilité).

## Modalités de remise

Cinq **PDF autonomes**, leurs **fichiers sources .drawio**, dans `NOM_Prenom_Bloc4_AquaVigie.zip`. Utilisez les ressources fictives du présent dépôt. Les durées et modalités de l'établissement prévalent.

## Compétences visées

- **C14** architecture adéquate, diagrammes, argumentaire de qualité ;
- **C15** appropriation de l'existant, évolution pérenne et reprise par des tiers ;
- **C16** structures et algorithmes pertinents et robustes ;
- **C17** stratégie de tests multi-niveaux et non-régression ;
- **C18** données massives, ML, réseaux de neurones, optimisation/prédiction.

**Important :** l'énoncé modèle évalue C15 et C16 à travers des choix documentés ; il ne produit pas à lui seul une preuve de développement exécuté.