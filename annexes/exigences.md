# AquaVigie — exigences et hypothèses de dimensionnement

| Dimension | Hypothèse d'entraînement |
|---|---|
| Parc de capteurs | 2 400 capteurs sur plusieurs zones |
| Volume de pointe | Jusqu'à 8 millions de relevés par jour |
| Consultation cartographique / alertes | p95 < 600 ms en charge nominale |
| Disponibilité cible consultation | 99,9 % mensuel |
| Intégrité | Aucune perte silencieuse ; doublons maîtrisés |
| Sécurité | Gestion des interventions réservée aux agents habilités, authentification interservices |
| Prédiction | Estimation du risque d'incident hydraulique dans les 6 h |
| Pérennité | Migration progressive, réversible et documentée |

Ces chiffres sont **des hypothèses pédagogiques**, non des mesures de production.

## Contraintes fonctionnelles

- Les techniciens consultent zones, historique des capteurs et alertes, puis qualifient les incidents.
- Les événements IoT peuvent arriver **en retard**, **dans le désordre** ou **en doublon**.
- Le service de prédiction est optionnel pour les fonctions opérationnelles critiques ; son indisponibilité ne doit pas bloquer la consultation.
- Les opérations de validation d'incident doivent rester humaines et protégées par les habilitations.
- Les historisations doivent conserver les instants UTC ; la localisation métier ne doit pas modifier ces instants.

**Travail candidat :** justifier les arbitrages, expliquer les hypothèses ajoutées et concevoir les mécanismes de qualité. Ce document ne constitue **pas une architecture cible corrigée**.