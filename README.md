# homefarm 🌱

Monorepo pour concevoir, construire et piloter mes installations de culture en vue
de plus d'autonomie alimentaire : **hydroponie**, **aquaponie**, **pleine terre / serre**, etc.

Tout y est : documentation, fiches cultures, électronique (ESP32), pièces imprimées en 3D,
firmware et software de supervision.

## Organisation

| Dossier | Contenu |
|---------|---------|
| [`docs/`](docs/) | Vision, base de connaissances, décisions (ADR), guides, **sécurité** |
| [`crops/`](crops/) | Fiches cultures (YAML) : pH, EC, température, lumière, cycles |
| [`farms/`](farms/) | Une fiche par installation réelle + journal de bord |
| [`hardware/`](hardware/) | Schémas ESP32, capteurs, actionneurs, alimentation, BOM |
| [`mechanical/`](mechanical/) | Sources CAD, STL, profils d'impression 3D |
| [`firmware/`](firmware/) | Code des nœuds ESP32 |
| [`software/`](software/) | Supervision : infra, services, dashboards |
| [`tools/`](tools/) | Scripts utilitaires (calculs nutritifs, génération STL…) |

## Démarrer
1. Lire [`docs/vision/`](docs/vision/) et [`docs/safety/`](docs/safety/)
2. Les choix techniques ouverts sont listés dans [`docs/decisions/0001-choix-a-trancher.md`](docs/decisions/0001-choix-a-trancher.md)
