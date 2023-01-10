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

- 5 Deploy jenkins with master and slave using helm chart
  - helm install --name my-release stable/jenkins
  - kubectl get svc my-release-jenkins -o=jsonpath='{.spec.ports[?(@.port==8080)].nodePort}'
  - printf $(kubectl get secret --namespace default my-release-jenkins -o jsonpath="{.data.jenkins-admin-password}" | base64 --decode);echo

  - ![image](https://user-images.githubusercontent.com/113102456/211533444-a1578a77-70b5-4dd7-8b82-d46d77daad90.png)
  - ![image](https://user-images.githubusercontent.com/113102456/211533545-fc8cbbd3-b571-4797-9de5-b07998bc660e.png)
  - ![image](https://user-images.githubusercontent.com/113102456/211533716-82ba78b6-2c3b-47a0-8cf1-dc9d21de4334.png)

 



