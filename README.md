# K8S-Depoly

- 1 Deploy a new container of SuperSet application:
  - kubectl create deployment superset --image=amancevice/superset
- 2  Create service for it and expose it.:
  - kubectl expose deployment superset --type=NodePort --port=8088
  - ![image](https://user-images.githubusercontent.com/113102456/211503487-f79d02cd-1f46-4b01-a061-7ea3f6f9820c.png)
