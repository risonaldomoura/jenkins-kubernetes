# jenkins-kubernetes

## Overview
jenkins-kubernetes is a [jenkins](https://www.jenkins.io/) deploy application for Kubernets and docker using kind

## Requirements

- [Kind](https://kind.sigs.k8s.io/)
- [kubernetes](https://kubernetes.io/)
- [Docker](https://www.docker.com/)

## How to build

1. Create a [cluster](https://kubernetes.io/pt-br/docs/concepts/overview/components/) running  `kind create cluster --name {NAME_CLUSTER}`
2. Create a [namespace](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/) running  `kind create namespace {NAMESPACE}`
3. Create a [deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) using [`deployment.yaml`](deployment.yaml) running  `kubectl create -f deployment.yaml -n {NAMESPACE}`
4. Create a [service](https://kubernetes.io/docs/concepts/services-networking/service/) using [`service.yaml`](service.yaml) running  `kubectl apply -f service.yaml -n {NAMESPACE}`
5. Get pod name `NAME_POD` running  `kubectl get pods -n {NAMESPACE}`
6. Exposed application in port `8080` running  `kubectl port-forward {NAME_POD} 8080 -n {NAMESPACE}`
7. Access application in browser in address `127.0.0.1:8080`
8. Get admin user jenkins password running  `kubectl logs {NAME_POD} -n {NAMESPACE}`
9. Be happy :)

## License

[Apache License 2.0](https://github.com/kubernetes/ingress-nginx/blob/main/LICENSE)