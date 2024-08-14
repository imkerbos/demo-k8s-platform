### Add repository
```
$ helm repo add istio https://istio-release.storage.googleapis.com/charts
$ helm repo update istio
```

### Create Namespace
```
$ kubectl create namespace istio-system
```

### Install chart
```
$ helm install istio-base istio/base -n istio-system
$ helm install istiod istio/istiod -n istio-system --wait
$ helm install istio-ingress istio/gateway -n istio-system --wait
```

### Using Gateways and Virtual Services
```
$ kubectl apply -f main-gw.yaml 
$ kubectl apply -f demo-virtualservice.yaml
```

### Using NetworkPolicy
```
$ kubectl apply -f auth-policy-global.yaml
```
