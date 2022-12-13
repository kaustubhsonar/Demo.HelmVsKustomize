# Helm Vs Kustomize

## Kustomize 
Kustomize is a Kubernetes configuration transformation tool that enables you to <b>customize untemplated YAML files</b>, leaving the original files untouched.
Kustomize relies on configuration layring to achieve reusability
- Base layer - Specifies the most common resources
- Patch layers - Specifies use case specific resources
### Kustomize Features
- <b>Kubectl Native</b>- No need to install or manage as a separate dependency
- <b>Plain Yaml</b>- No complex templating language
- <b>Declarative</b>- Purely declarative (just like Kubectl)
- <b>Multiple Configurations</b>- Manages any number of different configurations


## Helm 
Helm is widely known as <b>"the package manager for Kubernetes".</b> Helm is an open-source project which was originally created by DeisLabs and donated to CNCF, which now maintains it.
<p>Helm came up with the <b>idea of charts</b> to manage the kuberneters yaml files in the better way. 

### Helm features 
- Repository for many <b>readymade official charts</b> https://artifacthub.io/
- Can be used as a <b>package manager</b> for the application. 
- Provides easy <b>rollback, history, verison</b> for the whole application.
- Provides features to create charts of the application.
- Template support for reusability.


## Comparison 
| Functionality | Kustomize | Native Helm |
| -- | -- | -- |
| Templating | No templating | Complex templating |  
| Setup | No separate setup | Needs setup |
| Configuration | Manage multiple configurations with one base file | Manage multiple configurations with one base file |
| Ease of Use | Easy learning curve | More difficult compared to the other two |

## Command reference
### Kustomize commands

- kustomize build kustomize/overlays/dev > deploy-kustomize.yaml 
- kubectl apply -k kustomize/overlays/dev 

### Helm commands
- helm create helm-deployment
- helm template demo-helm -f helm/helm-deployment/values-dev.yaml ./helm/helm-deployment/ > deploy-helm.yaml 
- helm upgrade --install demo-helm -f helm/helm-deployment/values-dev.yaml -n dev ./helm/helm-deployment/
- helm list
- helm history demo-helm 