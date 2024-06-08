# frameworks
**kind**
+ version: v0.23.0
+ image: docker.io/kindest/node:v1.30.0

**kubectl**
+ version: v1.30.0

**helmfile**
+ version: v0.159.0

# deployment
+ in the cluster folder: kind create cluster --config ./kind-cluster.yaml
+ in the platform folder:
  + kubectl apply --server-side -k ./
  + helmfile init --file ./helmfile.yaml
  + helmfile apply --file ./helmfile.yaml

# components
**percona**
+ pg-operator:
  + version: 2.3.5
  + image: docker.io/percona/percona-postgresql-operator:2.3.1
+ pg-db:
  + version: 2.3.18
  + image: docker.io/percona/percona-postgresql-operator:2.3.1-ppg16-postgres-gis
