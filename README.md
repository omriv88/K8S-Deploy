# K8S-Depoly

- 1 Deploy a new container of SuperSet application:
  - kubectl create deployment superset --image=amancevice/superset
  
- 2  Create service for it and expose it.:
  - kubectl expose deployment superset --type=NodePort --port=8088
  - ![image](https://user-images.githubusercontent.com/113102456/211503621-674e65c0-ac2d-4ad5-b709-13d95f9bb973.png)
  - ![image](https://user-images.githubusercontent.com/113102456/211503674-e9336d2d-70cd-4a9e-bcf7-0ec681097ae8.png)
  
- 3 Do it with YAML and with scripted way:
  - https://github.com/omriv88/K8S-Depoly/blob/main/Deployment.yaml
  - https://github.com/omriv88/K8S-Depoly/blob/main/services.yaml

- 4 Deploy also Airflow application and expose it:
  - (https://hub.docker.com/r/puckel/docker-airflow/)
  - Create:
    - kubectl create deployment airflow --image=puckel/docker-airflow
  - Expose:
    - kubectl expose deployment airflow --type=NodePort --port=8088
