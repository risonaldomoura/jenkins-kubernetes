# jenkins-kubernetes

## Overview
jenkins-kubernetes is a [jenkins](https://www.jenkins.io/) deploy application for Kubernets and docker using kind

## Requirements

- Kind
- kubernetes
- Docker

## How to build

1. Create a [cluster](https://kubernetes.io/pt-br/docs/concepts/overview/components/) running command `kind create cluster --name {NAME_CLUSTER}`
2. Create a [namespace](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/) running command `kind create namespace {NAMESPACE}`
3. Execute [`deployment.yaml`](deployment.yaml) running command  `kubectl create -f deployment.yaml -n {NAMESPACE}`
4. Execute [`service.yaml`](service.yaml) running command  `kubectl apply -f service.yaml -n {NAMESPACE}`
5. Get pod name `NAME_POD` running command `kubectl get pods -n {NAMESPACE}`
6. Exposed application in port `8080` running command `kubectl port-forward {NAME_POD} 8080 -n {NAMESPACE}`
7. Access application in browser in address `127.0.0.1:8080`
8. Get admin user jenkins password running command `kubectl logs {NAME_POD} -n {NAMESPACE}`
9. Be happy :)

## License

[Apache License 2.0](https://github.com/kubernetes/ingress-nginx/blob/main/LICENSE)