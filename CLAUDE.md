# CLAUDE.md

Monorepo personnel de gestion de cultures (hydroponie, aquaponie, pleine terre…) visant
l'autonomie alimentaire. Mélange documentation, électronique ESP32, impression 3D, firmware
et software. On construit les plans **ensemble, itérativement** : proposer, expliquer les
compromis, puis attendre validation avant les choix structurants.

## Langue
- Documentation, fiches, journal, ADR : **français**.
- Code, identifiants, noms de fichiers, messages de commit : **anglais** (sauf dossiers de docs déjà en français).

## Architecture
- `docs/` — `vision/`, `knowledge/<technique|thème>/`, `decisions/` (ADR numérotées), `guides/`, `safety/`
- `crops/` — une fiche YAML par plante, basée sur `crops/_template.yaml`. **Source de vérité** des
  consignes (pH, EC, temp, lumière) : le firmware/software doit les lire, pas les dupliquer en dur.
- `farms/<nom>/` — une installation physique réelle (créée depuis `farms/_template/`), avec journal daté.
- `hardware/` — `nodes/` (KiCad), `sensors/`, `actuators/`, `power/`, `bom/` (CSV), `datasheets/`
- `mechanical/` — `cad/` (sources), `stl/` (exports), `print-profiles/`
- `firmware/` — `lib/` (partagé), `nodes/<type-de-noeud>/` (un projet par type de nœud)
- `software/` — `infra/` (docker-compose), `services/`, `dashboards/`
- `tools/` — scripts utilitaires

## Conventions
- Noms de fichiers et dossiers en `kebab-case`.
- Journal et entrées datées : `AAAA-MM-JJ-sujet.md`.
- Décision structurante (framework, protocole, outil, choix de système) → nouvelle ADR dans
  `docs/decisions/` à partir de `0000-template.md`. Ne pas modifier une ADR acceptée ; la remplacer.
- Les choix encore ouverts sont dans `docs/decisions/0001-choix-a-trancher.md` : ne pas
  présumer d'une réponse (ex. ESPHome vs PlatformIO) tant qu'une ADR ne l'a pas acceptée.
- 3D : toujours versionner la **source** CAD à côté du STL ; un STL sans source est une dette.
- BOM : CSV avec colonnes `ref,description,qty,unit_price_eur,supplier,url,notes`.
- Valeurs agronomiques (pH, EC, DLI…) : citer la source dans le champ `sources` ou en note.

## Règles de sécurité (non négociables)
Voir `docs/safety/README.md`. En résumé, pour tout design hardware ou firmware :
- Eau + 230V : différentiel 30 mA, 230V hors zone humide, boîtiers IP adaptés. Signaler
  explicitement tout montage qui touche au secteur.
- **Fail-safe** : chaque nœud a un état sûr au boot, en crash et en perte réseau.
  La logique vitale (coupure niveau bas, durée max des pompes de dosage, aération des poissons)
  tourne **localement sur l'ESP32**, jamais uniquement côté serveur.
- Watchdog activé ; tout actionneur a un timeout.
- Matériaux au contact de l'eau : qualité alimentaire (PETG/ASA en impression, pas de PLA).

## Secrets
WiFi, MQTT, tokens : jamais commités. Fichiers `secrets.yaml` / `secrets.h` / `.env` ignorés ;
fournir un `*.example` à la place.

## Commandes
Aucune pour l'instant — à compléter quand firmware/software seront initialisés
(build, flash, lint, tests, lancement de la stack).
