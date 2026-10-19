1. **Pod autonome vs Deployment** : un Pod autonome supprimé disparaît définitivement. Un Pod géré par un Deployment est recréé automatiquement, et on peut changer son nombre de réplicas.

2. **Rôle du ReplicaSet** : il vérifie en continu que le nombre de Pods voulu (ex. 3) est atteint. Si un Pod disparaît, il en recrée un.

3. **Rôle du Service** : il donne une adresse stable pour joindre les Pods et répartit le trafic entre eux. Il trouve les Pods grâce à leurs labels (`app: whoami`). On vérifie avec `kubectl get endpoints whoami-service`, qui doit lister les IP des Pods.

4. **Image dans Minikube + `imagePullPolicy: Never`** : l'image est construite sur notre machine, donc Minikube ne la connaît pas. `minikube image load` la copie dans le cluster. `Never` empêche Kubernetes d'aller la chercher sur Docker Hub, où elle n'existe pas.