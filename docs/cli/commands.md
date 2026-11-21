# Manuel des Commandes CLI Sovrack

Le CLI Sovrack (`sovrack`) permet d'orchestrer vos déploiements et de gérer vos infrastructures directement depuis votre terminal de développement.

## Installation du CLI

```bash
npm install -g @sovrack/cli
```

## Commandes Principales

### `sovrack login`
Connecte votre terminal à votre instance Sovrack locale ou hébergée :
```bash
sovrack login --url https://app.sovrack.com --token <VOTRE_PAT>
```

### `sovrack deploy`
Déploie le projet du répertoire courant vers un serveur cible :
```bash
sovrack deploy --target vps-production --env production
```

### `sovrack status`
Affiche l'état des conteneurs, l'utilisation CPU/RAM et les certificats TLS :
```bash
sovrack status --project mon-api
```

### `sovrack logs`
Suit les journaux d'exécution en temps réel :
```bash
sovrack logs --follow --service api-production
```

### `sovrack ssh`
Ouvre une session SSH sécurisée vers le serveur hébergeant le conteneur :
```bash
sovrack ssh --server vps-production
```
