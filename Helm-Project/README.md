### Helm Configuration

```
    curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
    chmod 700 get_helm.sh
    ./get_helm.sh
```

**resource**:  https://helm.sh/docs/intro/install/


### EBS drivers Install by Helm


Helm
Add the aws-ebs-csi-driver Helm repository.
```    
    helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver
    helm repo update
```
Install the latest release of the driver.
```
    helm upgrade --install aws-ebs-csi-driver \
        --namespace kube-system \
        aws-ebs-csi-driver/aws-ebs-csi-driver
```


**resource**: https://github.com/kubernetes-sigs/aws-ebs-csi-driver/blob/master/docs/install.md


### Attach Policy attach to Nodes IAM role for EBS csi driver access

### Create storage class

```
    kubectl create -f EBS-storage-class.yaml
```    

### Create Namespace
```
    kubectl apply -f namespace.yaml
```

### Change Default namespace 
```
    sudo git clone https://github.com/ahmetb/kubectx /opt/kubectx
    sudo ln -s /opt/kubectx/kubectx /usr/local/bin/kubectx
    sudo ln -s /opt/kubectx/kubens /usr/local/bin/kubens
```

```
kubens robokart
```

**resource**: https://github.com/ahmetb/kubectx


### K9 install for UI view of pods

```
curl -sS https://webinstall.dev/k9s | bash

```
steps:
    - take new tab
    - command ``` k9s```
**resource**:  https://github.com/derailed/k9s