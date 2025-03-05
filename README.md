# nkp-traefiklabs-catalog

this catalog allows to upgrade default traefik instance to traefik hub.  

procedure:
- create a new catalog in your cluster by launching the following command

```
kubectl apply -k https://github.com/traefik/nkp-traefiklabs-catalog/hub
```

- connect to traefik hub dashboard, create a new gateway and retrieve the corresponding token

```
TRAEFIK_HUB_TOKEN=XXXXXXX
```

- create a new secret in your cluster with the token

```
kubectl create secret generic license --namespace kommander --from-literal=token=$TRAEFIK_HUB_TOKEN
```

- install the traefik hub catalog entry

