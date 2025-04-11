
# Interface de Monitoring Embarqué

## État Actuel du Projet

En raison des contraintes de temps et de ressources, seules les fonctionnalités essentielles ont été implémentées :

### Fonctionnalités Opérationnelles

1. **Acquisition des Données**
   - Réception des données via MQTT depuis le dispositif ESP32
   - Topic MQTT : "patient/esp32-c40a24/data"
   - Paramètres surveillés : température, pouls, créatinine

2. **Stockage des Données**
   - Persistance dans InfluxDB Cloud
   - Organisation : ac9c12a5970cc113
   - Bucket : Hackathon

3. **Interface Utilisateur**
   - Dashboard principal avec affichage en temps réel
   - Graphiques d'évolution des paramètres
   - Système d'alertes basé sur des seuils

### Architecture Technique

- **Frontend** : React + TypeScript
- **Backend** : Express.js
- **Communication** : MQTT via HiveMQ
- **Base de données** : InfluxDB Cloud

### Flux de Données
1. L'ESP32 envoie les données via MQTT
2. Le serveur Node.js reçoit et traite les données
3. Stockage dans InfluxDB Cloud
4. Affichage en temps réel sur le dashboard

### Limitations Actuelles
- Interface limitée au dashboard principal
- Fonctionnalités avancées de gestion des dispositifs non implémentées
- Configuration des seuils d'alerte simplifiée
- Authentification basique

## Démarrage

```bash
npm install
npm run dev
```

Le serveur démarre sur le port 5000 et l'interface est accessible via le navigateur.
