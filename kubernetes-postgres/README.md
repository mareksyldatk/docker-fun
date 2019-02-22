# Running `postgres` on `kubernetes`

[Tutorial page](https://severalnines.com/blog/using-kubernetes-deploy-postgresql)

Create postgres config map resources

```
kubectl create -f postgres-configmap.yaml
```

Create storage related deployments

```
kubectl create -f postgres-storage.yaml
```

Create postgres deployment

```
kubectl create -f postgres-deployment.yaml 
```

Create Postgres Service

```
kubectl create -f postgres-service.yaml 
```

Connect to PostgreSQL

- Get Node port
    ```
    kubectl get svc postgres
    ```
- Connect
    ```
    psql -h localhost -U postgresadmin --password -p 31238 postgresdb
    ```

Delete PostgreSQL Deployments

```
kubectl delete service postgres 
kubectl delete deployment postgres
kubectl delete configmap postgres-config
kubectl delete persistentvolumeclaim postgres-pv-claim
kubectl delete persistentvolume postgres-pv-volume
```