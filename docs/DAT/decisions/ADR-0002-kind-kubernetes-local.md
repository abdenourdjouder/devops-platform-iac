# ADR-0002 — Kind pour Kubernetes local

- **Statut :** Accepté
- **Date :** 2026-11-08
- **Projet :** Modern DevOps Platform

## Contexte

Le projet nécessite un environnement Kubernetes local, reproductible, versionné dans Git et compatible avec Docker Desktop sous WSL2.

Cet environnement doit permettre de tester les déploiements, les pipelines CI/CD, GitOps, la sécurité et l'observabilité.

## Solutions étudiées

### Kind

- Exécute les nœuds Kubernetes dans des conteneurs Docker.
- Permet de créer des clusters multinœuds.
- Adapté à l'automatisation et aux tests CI/CD.
- Configuration déclarative et versionnable.

### Minikube

- Prend en charge différents drivers.
- Propose des add-ons intégrés.
- Adapté au développement et à l'apprentissage Kubernetes.
- Offre davantage de fonctionnalités prêtes à l'emploi.

## Décision

Adopter **Kind (Kubernetes IN Docker)** pour l'environnement Kubernetes local.

Docker Desktop restera le moteur Docker unique, conformément à l'ADR-0001.
![Description de l'image](images/ADR-0002-kind-kubernetes.png)
## Justification

- Compatibilité avec notre environnement WSL2 et Docker Desktop.
- Reproductibilité des clusters.
- Simplicité de création et de destruction.
- Possibilité de tester des topologies multinœuds.
- Intégration aux futurs workflows CI/CD et GitOps.

## Conséquences

### Avantages

- Configuration du cluster versionnée dans Git.
- Automatisation facilitée.
- Environnement local isolé et reproductible.
- Pas de machine virtuelle supplémentaire à gérer directement.

### Contraintes

- Certaines fonctionnalités cloud managées ne sont pas disponibles localement.
- Le stockage, le réseau et l'exposition des services nécessitent une configuration adaptée.
- Les ressources CPU et mémoire doivent être surveillées.

## Stratégie de déploiement

1. Installer Kind dans Ubuntu WSL2.
2. Créer une configuration déclarative du cluster.
3. Déployer initialement une topologie légère.
4. Vérifier les nœuds, pods système et accès kubectl.
5. Documenter les commandes de création et de destruction.
6. Étendre ultérieurement la topologie si nécessaire.

## Validation

Décision d'architecture enregistrée.

**Le cluster Kind n'est pas encore installé ni déployé.**