# 0001 — Choix structurants à trancher

- **Statut** : proposée
- **Date** : 2026-10-22

Liste des décisions ouvertes. Chacune donnera lieu à sa propre ADR une fois tranchée.

1. **Framework firmware** : ESPHome (YAML, intégration Home Assistant native, très rapide)
   vs PlatformIO + Arduino/ESP-IDF (contrôle total, logique locale complexe).
2. **Protocole** : MQTT (broker Mosquitto) vs API native ESPHome.
3. **Supervision** : Home Assistant vs stack dédiée (Node-RED + InfluxDB/TimescaleDB + Grafana).
4. **Hébergement** : Raspberry Pi / mini-PC local / serveur existant.
5. **Outil CAD** : OpenSCAD (paramétrique, texte, diffable) vs FreeCAD vs autre.
6. **Outil électronique** : KiCad (recommandé, open-source) pour schémas et PCB.
7. **Premier système** : DWC (le plus simple), NFT, ou Kratky (sans pompe) pour démarrer.
