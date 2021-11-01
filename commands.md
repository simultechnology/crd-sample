
## Create Simple CRD YAML
```
kubectl get crds
kubectl get thermometers

kubectl apply -f assets/thermometer-crd-minimal.yaml

kubectl get crds
kubectl api-resources --api-group='d2iq.com' -o wide

kubectl get --raw / | jq . | grep -C3 d2iq
kubectl get -v=9 --raw /apis/d2iq.com/v1beta1/thermometers/ | jq

kubectl get trms
```

## Apply Simple Resource
```
kubectl apply -f assets/thermometer.yaml
kubectl get trms -A

kubectl delete trm -n default --all
kubectl get trm -A
```

## Apply Resource with Spec

```
kubectl create namespace sweden
kubectl apply -f assets/stockholm-thermometer.yaml --validate=false

kubectl get trm -A
kubectl get trm stockholm -n sweden -o json | jq
```
## Exposing Resource Columns

```
kubectl apply -f assets/thermometer-crd-with-columns.yaml
kubectl get trm -A
```

## Validate Declaration of Resource

```
kubectl apply -f assets/gothenburg-thermometer.yaml

```
