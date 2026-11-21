# Démarrage Rapide (Quickstart)

Bienvenue sur la documentation officielle de **Sovrack**. Ce guide vous explique comment installer Sovrack sur votre serveur Ubuntu et déployer votre première application en moins de 5 minutes.

## Prérequis

- Un serveur VPS ou dédié sous **Ubuntu 22.04 LTS** ou **Ubuntu 24.04 LTS** (OVH, Hetzner, Scaleway ou machine virtuelle locale).
- Accès root ou utilisateur avec privilèges `sudo`.
- Au minimum 1 vCPU et 2 Go de RAM.
- Ports 80 (HTTP) et 443 (HTTPS) ouverts.

## Étape 1 : Installation automatique en 1 ligne

Connectez-vous en SSH à votre serveur et exécutez la commande suivante :

```bash
curl -fsSL https://get.sovrack.com | bash
```

Le script configure automatiquement Docker, le reverse proxy et démarre la plateforme Sovrack.

## Étape 2 : Création de votre compte administrateur

Une fois l'installation terminée, accédez à votre console web :

```
http://<IP-DE-VOTRE-SERVEUR>:3000
```

Suivez l'assistant d'accueil pour :
1. Définir votre mot de passe administrateur.
2. Configurer votre premier espace de travail.
3. Lier votre compte GitHub ou GitLab.

## Étape 3 : Déployer votre premier service

1. Cliquez sur **Nouveau projet**.
2. Sélectionnez votre dépôt Git ou entrez une URL de dépôt public.
3. Sovrack détecte automatiquement votre runtime (Node.js, Next.js, Python, Go, etc.) via Nixpacks.
4. Cliquez sur **Déployer**.

Votre application est construite dans un conteneur Docker isolé et routée automatiquement avec un certificat HTTPS Let's Encrypt !
