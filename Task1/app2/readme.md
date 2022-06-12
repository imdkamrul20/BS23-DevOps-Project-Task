Create deployment and service in same yaml file.

Create ConfigMap
kubectl apply -f dbenv-configMap.yaml

Set both node lables name

kubectl label node worker-node1 operation=node1
kubectl label node worker-node2 operation=node2
