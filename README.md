
# Interface de Monitoring Embarqué

## État Actuel du Projet

En raison des contraintes de temps et de ressources, seules les fonctionnalités essentielles ont été implémentées.

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

## Fonctionnalités Principales

### 1. Tableau de Bord (/dashboard)
- Affichage en temps réel des mesures :
  - Température corporelle
  - Pouls
  - Taux de créatinine
- Graphiques d'évolution temporelle
- Tableaux de données historiques

### 2. Gestion des Dispositifs (/devices)
- Liste des matelas connectés
- État de connexion
- Informations sur le patient
- Assignation des chambres

### 3. Alertes (/alerts)
- Système de notification en temps réel
- Seuils d'alerte configurables
- Historique des alertes
- Classification par niveau de gravité

### 4. Paramètres (/settings)
- Configuration des seuils d'alerte
- Gestion des périodes de rétention
- Paramètres de fréquence d'échantillonnage

## Sécurité
- Authentification MQTT
- Stockage sécurisé des tokens
- Validation des données
- Protection des routes sensibles

## Interface Utilisateur
- Design responsive
- Thème clair/sombre
- Composants modulaires
- Indicateurs visuels d'état

## Démarrage

```bash
npm install
npm run dev
```

Le serveur démarre sur le port 5000 et l'interface est accessible via le navigateur.

## Configuration Technique

### MQTT
- Broker : broker.hivemq.com
- Port WebSocket : 8884 (WSS)
- Topic : patient/esp32-c40a24/data

### InfluxDB
- URL : https://eu-central-1-1.aws.cloud2.influxdata.com
- Organisation : ac9c12a5970cc113
- Bucket : Hackathon
