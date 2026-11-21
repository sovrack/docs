# Architecture de Sovrack

Sovrack repose sur une architecture moderne **open-core sans agent (agentless)**, pensée pour garantir une souveraineté totale et zéro dépendance lourde sur vos serveurs de production.

## Schéma d'Architecture

```
┌────────────────────────────────────────────────────────┐
│                   SOVRACK MASTER                       │
│  ┌─────────────────────────┐  ┌─────────────────────┐  │
│  │   Next.js 15 Web App    │  │  NestJS Backend API │  │
│  └─────────────────────────┘  └──────────┬──────────┘  │
│                                          │             │
│                         Encrypted SSH ───┘             │
└──────────────────────────────────┼─────────────────────┘
                                   │
         ┌─────────────────────────┼─────────────────────────┐
         ▼                         ▼                         ▼
┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│ TARGET VPS 1    │       │ TARGET VPS 2    │       │ TARGET VPS 3    │
│ (Production)    │       │ (Staging)       │       │ (Base de données│
│ • Docker Engine │       │ • Docker Engine │       │ • PostgreSQL 16 │
│ • Traefik Proxy │       │ • Preview Envs  │       │ • Volumes pers. │
└─────────────────┘       └─────────────────┘       └─────────────────┘
```

## Principes Fondamentaux

1. **Zéro Agent Lourd (Agentless)** : Aucun démon consommateur de mémoire n'a besoin d'être installé sur vos serveurs cibles. Sovrack orchestre Docker au travers de sessions SSH directes et chiffrées avec des clés ED25519.
2. **Build Universel avec Nixpacks** : Détection sans configuration des technologies modernes (Next.js Standalone, Node.js, Python FastAPI/Django, Golang, Rust, PHP Laravel/Symfony, etc.).
3. **Routage Dynamique & Certificats TLS** : Automatisation complète des sous-domaines et des certificats SSL/TLS via Let's Encrypt (renouvellement transparent tous les 60 jours).
4. **Isolation Stricte des Conteneurs** : Réseaux Docker dédiés par projet, quotas CPU et RAM configurables, et stockage de volumes chiffré.
