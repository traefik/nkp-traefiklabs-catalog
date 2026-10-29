# nkp-traefiklabs-catalog

> [!WARNING]
> **This repository is deprecated and will be archived.** It is no longer maintained and will not receive updates.
>
> Traefik Hub for Nutanix Kubernetes Platform (NKP) is now published in the official NKP partner catalog:
> **https://github.com/nutanix-cloud-native/nkp-partner-catalog/tree/main/applications/traefik-hub**

## Why this repository is deprecated

- The official NKP partner catalog, maintained with Nutanix, is the supported way to install Traefik Hub on NKP.
- This catalog pins Traefik Hub v3.14.1 and has not been updated since March 2025. It does not receive newer Traefik Hub releases.

## If you use this catalog

Do not add this catalog to new clusters. For new installations, use the NKP partner catalog linked above.

If a cluster already uses this catalog:

- It keeps working. Archiving makes the repository read-only, so the `traefik-hub-catalog` GitRepository in the `kommander` namespace can still sync it.
- The catalog will not receive new Traefik Hub versions or security fixes. Plan a migration to the NKP partner catalog.
- After migrating, uninstall the Traefik Hub application deployed from this catalog, then remove the catalog:

  ```shell
  kubectl delete gitrepository traefik-hub-catalog --namespace kommander
  ```

## Documentation
- Traefik Hub on NKP: https://doc.traefik.io/traefik-hub/api-gateway/setup/installation/nkp
