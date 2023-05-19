# Applying Sonatype Nexus as a Deployment

> [Sontype Nexus](https://hub.docker.com/r/sonatype/nexus3/) docker image
> I am using docker desktop


## 1.1 Deploy `nexus` k8s resources:

> Deploy `nexus` [ns](./nexus-ns.yaml)

```
kubectl apply -f nexus-ns.yaml
```

> Deploy `nexus` [pv](./nexus-pv.yaml)

```
kubectl apply -f nexus-pv.yaml
```
> Deploy `nexus` [pvc](./nexus-pvc.yaml)

```
kubectl apply -f nexus-pvc.yaml
```
> Deploy `nexus` [svc](./nexus-svc.yaml)

```
kubectl apply -f nexus-svc.yaml
```
> Deploy `nexus` [deployment](./nexus-deploy.yaml)

```
kubectl apply -f nexus-deploy.yaml
```
> Deploy `nexus` [Ingress](./nexus-ingress.yaml)

```
kubectl apply -f nexus-ingress.yaml
```
> go to http://nexus.local.com



> enable insecure registiry:
```
sudo vi /etc/docker/daemon.json

# paste below content:
{
  "insecure-registries" : ["docker.nexus.local.com"]
}

sudo systemctl restart docker
```
