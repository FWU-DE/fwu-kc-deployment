# FWU Keycloak deployment

Keycloak deployment for different environments using Helm.

# Environment

The GitHub workflow to run the deployment uses [environments](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment).

## Repository Secrets

| Name                   | Description                                                  | Example          |
| ---------------------- | ------------------------------------------------------------ | ---------------- |
| `NEXUS_THEME_USER`     | Username of the Nexus user that can pull the Keycloak theme. | `nx-user`        |
| `NEXUS_THEME_PASSWORD` | Password of the Nexus user that can pull the Keycloak theme. | `ZHjd782hsDKuih` |

## Secrets

Each environment must have the following secrets specified for the deployment:

| Name        | Description                              | Example           |
| ----------- | ---------------------------------------- | ----------------- |
| `HOSTNAME`  | Keycloak URL of the environment.         | `dev.example.com` |
| `NAMESPACE` | Kubernetes namespace to which to deploy. | `default`         |
| `KC_MIN_PODS` | Minimum number of Pods for autoscaling. | `3` |
| `KC_MAX_PODS` | Maximum number of Pods for autoscaling. | `10` |
| `VERSION` | Keycloak version to deploy. | `16.1.1` |
| `KC_EXT_VERSION` | Version for the Keycloak extensions from [this](https://github.com/FWU-DE/fwu-kc-extensions) repository. | `1.0.0` |
| `KC_USER` | Username of the Keycloak admin user. | `admin` |
| `KC_USER_PASSWORD` | Password of the Keycloak admin user. | `jisbandu8h98DH` |
| `KC_DB_ADDRESS` | Address of the PostgreSQL server to be used by Keycloak. | `pg183281.cloud.provider:5432` |
| `KC_DB_NAME` | Database name inside the PostgreSQL server for Keycloak data. | `keycloak` |
| `KC_DB_USER` | Username of the database user used for connecting. | `pgkeycloak` |
| `KC_DB_PASSWORD` | Password of the database user used for connecting. | `DJ+h78dhh321hdjss` |
| `KUBE_CONFIG` | Base64 encoded Kubernetes config used for connecting to the cluster.<br />`cat $HOME/.kube/config \| base64`<br /> See [here](https://github.com/wahyd4/kubectl-helm-action#how-to-use) | *** |
