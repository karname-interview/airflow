# Airflow

## Installation 

Change the following fields in `values.yaml`
- `airflow.config.AIRFLOW__WEBSERVER__BASE_URL`
- `airflow.config.AIRFLOW__KUBERNETES_ENVIRONMENT_VARIABLES__AIRFLOW__WEBSERVER__BASE_URL`
- `ingress.web.host`
- `dags.gitSync.repo`: should be the same as `DAG_REPO` mentioned in [this repo](https://github.com/karname-interview/readme)

Run the following commands
```bash 
RELEASE_NAME=air 
NAMESPACE=air
CHART_VERSION=8.4.0
VALUES_FILE=./values.yaml

helm repo add airflow-stable https://airflow-helm.github.io/charts
helm repo update
helm install $RELEASE_NAME airflow-stable/airflow --create-namespace --namespace $NAMESPACE --version $CHART_VERSION --values $VALUES_FILE
```
