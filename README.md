# TP Kubernetes — Minikube et Docker

**Binôme :** Cheick Coulibaly, Yoann DOSSOU-YOVO

## Versions
- Docker : 29.8.1
- kubectl : V1.36.1
- Minikube : V1.39.0

## Étapes réalisées
1. Démarrage du cluster Minikube (driver Docker)
2. Création du namespace `demo` et d'un Pod autonome
3. Deployment `whoami` à 3 réplicas, test d'auto-réparation et de scaling
4. Service ClusterIP `whoami-service`, test avec port-forward + curl
5. Image personnalisée `monapp:1.0` (nginx), chargée dans Minikube et déployée

## Difficultés rencontrées
- `kubectl exec -it whoami-pod -- sh` échoue : l'image whoami ne contient pas de shell. Hostname vérifié via port-forward + curl.
- (ajoutez les vôtres)