# rukpak-playground
Just to play with rukpak


## How to test

```
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.11.0/cert-manager.yaml
# Wait for the installation
kubectl apply -f https://github.com/operator-framework/rukpak/releases/download/v0.11.0/rukpak.yaml
# wait for the installation
# Installing olm
 kubectl apply -f olmv0/bundle.yaml
# Wait until you'll see this
 kubectl get bd
NAME              ACTIVE BUNDLE            INSTALL STATE           AGE
olmv0             olmv0-bdf4v8             InstallationSucceeded   13m

kubectl apply -f olmv1/bundle.yaml
kubectl get bd
NAME              ACTIVE BUNDLE            INSTALL STATE           AGE
olmv0             olmv0-bdf4v8             InstallationSucceeded   13m
olmv1             olmv1-59848f             InstallationSucceeded   13m

# Wait for the installation of OLM
kubectl apply -f operators/bundle.yaml 

# Wait until VM operator csv will be present
 kubectl get csv
NAME                                      DISPLAY                                                      VERSION   REPLACES                                  PHASE
percona-server-mongodb-operator.v1.14.0   Percona Distribution for MongoDB Operator                    1.14.0    percona-server-mongodb-operator.v1.13.1   Succeeded
percona-xtradb-cluster-operator.v1.12.0   Percona Operator for MySQL based on Percona XtraDB Cluster   1.12.0    percona-xtradb-cluster-operator.v1.11.0   Succeeded
victoriametrics-operator.v0.29.1          VictoriaMetrics Operator                                     0.29.1    victoriametrics-operator.v0.27.2          Succeeded
```

kubectl apply -f dbaas/bundle.yaml
