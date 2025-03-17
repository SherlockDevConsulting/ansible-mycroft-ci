# Rôle Ansible : Déploiement de Gitea

## 🔹 Objectifs
Ce rôle installe et configure **Gitea** avec **PostgreSQL** en utilisant **Docker Compose**.

## 🔹 Services et ports
| Service  | Port  |
|----------|-------|
| Gitea Web UI | `http://<server-ip>:3000` |
| Gitea SSH | `ssh -p 222 git@<server-ip>` |
| PostgreSQL | `5432 (interne, pas exposé)` |

## 🔹 Variables de configuration
Les valeurs par défaut sont définies dans `group_vars/all.yml` :

| Variable | Valeur par défaut | Description |
|----------|------------------|-------------|
| `gitea_version` | `"1.23.5"` | Version de Gitea |
| `postgres_version` | `"17"` | Version de PostgreSQL |
| `gitea_ports` | `"3000:3000", "222:22"` | Ports exposés |
| `gitea_db_user` | `"gitea"` | Utilisateur PostgreSQL |

## 🔹 Commandes utiles
Démarrer Gitea et PostgreSQL :
```bash
docker compose -f /opt/gitea/docker-compose.yml up -d
```

Arrêter Gitea et PostgreSQL :
```bash
docker compose -f /opt/gitea/docker-compose.yml down
```

Voir les logs :
```bash
docker logs gitea -f
```
