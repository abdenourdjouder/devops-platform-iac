
# Dossier d'Architecture Technique (DAT)

## Modern DevOps Platform

| Propriété | Valeur |
|---|---|
| Projet | Modern DevOps Platform |
| Dépôt | devops-platform-iac |
| Version DAT | 0.1.0 |
| Date initiale | 07/11/2026 |
| Statut | En construction |
| Environnement | Local — Windows 11 / WSL2 |

## 1. Présentation générale

Modern DevOps Platform est un laboratoire professionnel
destiné à construire une plateforme DevOps modulaire,
automatisée, sécurisée et reproductible.

Principes fondamentaux :

- Everything as Code
- Git as Source of Truth
- Documentation First
- Reusable by Design
- Destroyable by Design
- Security First

## 2. Objectifs techniques

- Automatiser les infrastructures avec Terraform et Ansible.
- Industrialiser les déploiements avec CI/CD.
- Déployer des applications conteneurisées.
- Implémenter Kubernetes et GitOps.
- Intégrer la sécurité aux pipelines.
- Mettre en place monitoring et observabilité.
- Documenter le cycle de vie des composants.

## 3. Environnement technique audité

### 3.1 Windows

| Ressource | Configuration |
|---|---|
| Système | Windows, build 26300.9711 |
| Processeur | Intel Core Ultra 7 258V |
| CPU | 8 cœurs / 8 processeurs logiques |
| RAM physique | 31,55 Go |
| Disque C: | 951,89 Go |
| Espace libre C: | 795,16 Go |

### 3.2 Ubuntu WSL2

| Ressource | Configuration |
|---|---|
| Distribution | Ubuntu 24.04.5 LTS |
| WSL | 3.0.3.0 |
| Noyau Linux | 6.18.54.1-1 |
| Init system | systemd |
| CPU visibles | 8 |
| RAM visible | 15 GiB |
| Swap | 4 GiB |
| Système de fichiers | 1007 GiB virtuels |

### 3.3 Docker

| Composant | Version |
|---|---|
| Docker Desktop | 4.98.0 |
| Docker Engine | 29.9.2 |
| Docker Compose | 5.6.1 |
| Storage Driver | overlayfs |

L'intégration Docker Desktop avec Ubuntu WSL2 est
fonctionnelle.

Aucun conteneur ni volume Docker existant lors de l'audit.

## 4. Architecture cible

Composants prévus :

- GitHub et GitHub Actions
- Terraform
- Ansible
- Docker Compose
- Jenkins
- SonarQube
- Trivy
- Kubernetes Kind
- Helm
- Argo CD
- Prometheus
- Grafana
- Loki
- OpenTelemetry

Cette liste représente l'architecture cible.
Ces composants ne sont pas encore tous installés.

## 5. Architecture réellement déployée

À la date de création du DAT :

- Ubuntu WSL2 opérationnel
- systemd actif
- Docker Desktop fonctionnel
- Git disponible
- Python 3 disponible
- kubectl disponible
- Authentification GitHub SSH validée
- Dépôt Git local initialisé

Aucune plateforme applicative DevOps encore déployée.

## 6. Principes d'exploitation

Chaque composant devra disposer de :

1. Une configuration versionnée.
2. Une procédure de déploiement.
3. Des tests de validation.
4. Une procédure d'arrêt.
5. Une procédure de destruction contrôlée.
6. Une stratégie de conservation des données.
7. Une documentation d'exploitation.

## 7. Sécurité

- Aucun secret dans Git.
- Authentification GitHub par SSH.
- Séparation des configurations et des credentials.
- Principe du moindre privilège.
- Analyse de sécurité des configurations et images.
- Contrôle des opérations destructives.

## 8. Décisions d'architecture

Les décisions seront enregistrées dans :

`docs/DAT/decisions/`

## 9. Prochaines étapes

- Finaliser l'initialisation Git.
- Publier le dépôt GitHub.
- Formaliser les premiers ADR.
- Concevoir les modules d'automatisation.
- Déployer progressivement les composants.

## 10. Historique

Voir `docs/DAT/changelog.md`.
