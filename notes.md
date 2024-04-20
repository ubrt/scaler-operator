# Installation 
selinux-policy-default, set SELINUX=disabled in /etc/selinux/config and reboot the system.

sudo snap install go --channel=1.21/stable --classic

https://sdk.operatorframework.io/docs/installation/

# Setup

operator-sdk init --plugins go/v4 --domain barrot.dev --owner "Ulrich Barrot" --repo github.com/ubrt/scaler-operator

operator-sdk create api --kind Scaler --group api --version v1alpha1

make manifests

kubectl apply -f config/crd/bases/api.barrot.dev_scalers.yaml

kubectl apply -f config/samples/api_v1alpha1_scaler.yaml

kubectl describe scalers.api.barrot.dev scaler-sample2