# thermometer

## Create Simple CRD YAML
```
kubectl get crds
kubectl get thermometers

kubectl apply -f assets/thermometer/thermometer-crd-minimal.yaml

kubectl get crds
kubectl api-resources --api-group='d2iq.com' -o wide

kubectl get --raw / | jq . | grep -C3 d2iq
kubectl get -v=9 --raw /apis/d2iq.com/v1beta1/thermometers/ | jq

kubectl get trms
```

## Apply Simple Resource
```
kubectl apply -f assets/thermometer/thermometer.yaml
kubectl get trms -A

kubectl delete trm -n default --all
kubectl get trm -A
```

## Apply Resource with Spec

```
kubectl create namespace sweden
kubectl apply -f assets/thermometer/stockholm-thermometer.yaml --validate=false

kubectl get trm -A
kubectl get trm stockholm -n sweden -o json | jq
```
## Exposing Resource Columns

```
kubectl apply -f assets/thermometer/thermometer-crd-with-columns.yaml
kubectl get trm -A
```

## Validate Declaration of Resource

```
kubectl apply -f assets/thermometer/gothenburg-thermometer.yaml

kubectl apply -f assets/thermometer/thermometer-crd-with-validation.yaml

kubectl apply -f assets/thermometer/gothenburg-thermometer.yaml
kubectl apply -f assets/sthermometer/tockholm-thermometer.yaml 

kubectl apply -f assets/thermometer/gothenburg-thermometer-valid.yaml
kubectl apply -f assets/thermometer/stockholm-thermometer-valid.yaml 

kubectl get trm -A
```

## Explain Command

```
kubectl explain namespace

kubectl explain thermometer
```
