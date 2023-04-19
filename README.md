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
```
