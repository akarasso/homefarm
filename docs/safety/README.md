# Sécurité

## Électricité + eau
- Tout circuit 230V protégé par un **différentiel 30 mA**.
- Basse tension (5/12/24V DC) au plus près de l'eau ; le 230V reste hors zone humide,
  dans des boîtiers IP adaptés (IP65+ près de l'eau).
- Pas de câblage 230V improvisé : relais certifiés, borniers, gaines, presse-étoupes.
- Pompes et chauffages immergés : matériel prévu pour l'immersion uniquement.

## Fail-safe
- Chaque nœud doit avoir un **état sûr par défaut** (au boot, en cas de crash, de perte réseau) :
  pompe de dosage OFF, chauffage OFF, aération/circulation selon le besoin vital des racines/poissons.
- Watchdog matériel activé ; limites de durée sur tout actionneur (ex. pompe de dosage max N secondes).
- Détection de niveau bas → coupure pompes (pas de pompe à sec, pas d'inondation).

## Alimentaire & produits
- Plastiques au contact de l'eau : qualité alimentaire (HDPE, PP, PETG). Éviter PVC souple, PLA (se dégrade).
- Acides/bases (pH up/down) et nutriments : stockage étiqueté, gants, lunettes.
- Aquaponie : surveiller ammoniaque/nitrites — une panne de pompe ou d'aération tue des poissons en quelques heures.
