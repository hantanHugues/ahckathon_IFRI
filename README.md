
# Interface de Monitoring Embarqué

## Documentation Complète de l'Interface

### Architecture Technique

#### Frontend (client/src/)
- **Framework** : React avec TypeScript
- **Style** : Tailwind CSS
- **Composants** : Interface modulaire avec composants réutilisables
- **État** : Gestion avec React Hooks et React Query

#### Backend (server/)
- **Serveur** : Express.js
- **Base de données** : InfluxDB Cloud
- **Communication** : MQTT via HiveMQ
- **Port** : 5000

### Fonctionnalités Prévues

#### 1. Tableau de Bord (/dashboard)
- Affichage en temps réel des mesures :
  - Température corporelle
  - Pouls
  - Taux de créatinine
- Graphiques d'évolution temporelle
- Tableaux de données historiques

#### 2. Gestion des Dispositifs (/devices)
- Liste des matelas connectés
- État de connexion
- Informations sur le patient
- Assignation des chambres

#### 3. Alertes (/alerts)
- Système de notification en temps réel
- Seuils d'alerte configurables
- Historique des alertes
- Classification par niveau de gravité

#### 4. Paramètres (/settings)
- Configuration des seuils d'alerte
- Gestion des périodes de rétention
- Paramètres de fréquence d'échantillonnage

### Configuration Technique

#### MQTT
- Broker : broker.hivemq.com
- Port WebSocket : 8884 (WSS)
- Topic : patient/esp32-c40a24/data

#### InfluxDB
- URL : https://eu-central-1-1.aws.cloud2.influxdata.com
- Organisation : ac9c12a5970cc113
- Bucket : Hackathon

### Démarrage

```bash
npm install
npm run dev
```

Le serveur démarre sur le port 5000 et l'interface est accessible via le navigateur.

## Fonctionnalités Actuellement Opérationnelles

En raison des contraintes de temps et de ressources, seules les fonctionnalités suivantes sont pleinement opérationnelles :

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
   - Système d'alertes basé sur des seuils
   - Graphiques d'évolution des paramètres
   - Statut de connexion MQTT

### Limitations Actuelles
- Interface limitée au dashboard principal
- Fonctionnalités avancées de gestion des dispositifs non implémentées
- Configuration des seuils d'alerte simplifiée
- Authentification basique
