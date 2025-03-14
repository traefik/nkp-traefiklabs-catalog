# nkp-traefiklabs-catalog

this catalog allows to upgrade default traefik instance to traefik hub.  

procedure:
- create a new catalog in your management cluster by launching the following command

```
kubectl apply -k https://github.com/traefik/nkp-traefiklabs-catalog/hub --kubeconfig=management-cluster.conf
```

- connect to traefik hub dashboard, create a new gateway and retrieve the corresponding token

```
TRAEFIK_HUB_TOKEN=XXXXXXX
```

- create a new secret in the cluster where you plan to upgrade Traefik to Traefik Hub.

```
kubectl create secret generic license --namespace workspace_namespace --from-literal=token=$TRAEFIK_HUB_TOKEN --kubeconfig=cluster1.conf
```

the secret must be created in the same namespace as the traefik instance (workspace's namespace)

- install the traefik hub catalog entry

https://doc.traefik.io/traefik-hub/api-gateway/setup/installation/nkp

