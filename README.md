# jenkins-kubernetes

## Overview
jenkins-kubernetes is a [jenkins](https://www.jenkins.io/) deploy application for Kubernets and docker using kind

## Requirements

- Kind
- kubernetes
- Docker

## How to build

1. Create a cluster running command `kind create cluster --name jenkins`
2. Create a namespace running command `kind create namespace jenkins`
3. Execute deployment.yaml running command  `kubectl create -f deployment.yaml -n jenkins`
4. Execute service.yaml running command  `kubectl apply -f service.yaml -n jenkins`
5. Get pod name NAME_POD running command `kubectl get pods -n jenkins`
6. Exposed application in port `8080` running command `kubectl port-forward {NAME_POD} 8080 -n jenkins`
7. Access application in browser in address `127.0.0.1:8080`
8. Get admin user jenkins password running command `kubectl logs {NAME_POD} -n jenkins`
9. Be happy :)

## License

[Apache License 2.0](https://github.com/kubernetes/ingress-nginx/blob/main/LICENSE)