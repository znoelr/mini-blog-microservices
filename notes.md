# Deploy individually
See [minikube](https://minikube.sigs.k8s.io/docs/commands/docker-env/) docs
Before executing kubectl run:
  - `minikube start --driver=docker`
  - `eval $(minikube docker-env)`

  Then build the images using docker
  Then run `kubectl apply -f <infra-dir>/k8s`

To install nginx ingress run:
  - `minikube addons enable ingress`

Get minikube ip, run:
  - `minikube ip`


# Deploy infra
Before deploy run:
  - `minikube start --driver=docker`
  - `eval $(minikube docker-env)`

Deploy command:
  ```
    docker image build -t mini-blog/posts:0.0.1 posts/ &&\
    docker image build -t mini-blog/query:0.0.1 query/ &&\
    docker image build -t mini-blog/moderation:0.0.1 moderation/ &&\
    docker image build -t mini-blog/comments:0.0.1 comments/ &&\
    docker image build -t mini-blog/event-bus:0.0.1 event-bus/ &&\
    docker image build -t mini-blog/client:0.0.1 client/ &&\
    kubectl delete -f infra/k8s/ &&\
    kubectl apply -f infra/k8s/
  ```


# Deploy with skaffold
See [skaffold](https://skaffold.dev/docs/init/) docs

Before init skaffold run:
  - `minikube start --driver=docker`
  - `eval $(minikube docker-env)`

To create skffold yaml:
  `skaffold init`

To start skaffold:
  `skaffold dev`
