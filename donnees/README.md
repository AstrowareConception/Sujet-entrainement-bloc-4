# Jeu de données fictif AquaVigie

Ce mini-échantillon illustre les **champs** et certains cas limites, pas les 8 millions de relevés/jour. Il ne prétend ni représenter une distribution industrielle, ni être suffisant pour entraîner un modèle.

`mesures_exemple.csv` contient :
- `sensorId`, `zoneId` : identifiants fonctionnels ;
- `capturedAt`, `receivedAt` : horodatages UTC d'acquisition et de réception ;
- `pressureBar`, `flowM3h` : mesures ;
- `valveState`, `recentIntervention` : état et intervention antérieure ;
- `incidentWithin6h` : **étiquette historique calculée a posteriori**, jamais connue lors de la prédiction.

Deux cas sont volontaires : **doublon d'une mesure** et **réception retardée**. Les candidats doivent choisir et expliquer la clé de déduplication, les règles de retard/ordre et le calcul des caractéristiques temporelles.

La colonne `incidentWithin6h` doit être exclue des variables prédictives : l'utiliser directement comme entrée serait une **fuite de données**. Le plan de test d'un système ML doit employer un découpage chronologique et mesurer l'impact métier des faux positifs/faux négatifs.

Les exemples ne sont **pas** des données personnelles ni de vraies données d'un réseau d'eau.