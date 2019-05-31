# drone-demo

Follow [Drone documentation](https://docs.drone.io/installation/github/kubernetes/) to setup Drone in Kubernetes cluster with Github:

Current setup is only for demo / test purposes:

- No https cert is configured
- Drone database is not persisted to any volume

How to setup Drone to Kubernetes cluster:

1. Deploy drone service with lb: `kubectl apply -f drone-service.yaml`

2. Create github oauth and update the values in the `secrets.yaml`

3. Deploy secrets: `kubectl apply -f secrets.yaml`

4. Deploy drone deployment (check drone host and other env values in the manifest): `kubectl apply -f drone.yaml`

5. Deploy rbac so that drone can run the pipeline pods `kubectl apply -f drone-rbac.yaml`
