# Quick Reference
You can do a quick autocomplete setup by the link below,
https://kubernetes.io/docs/reference/kubectl/quick-reference/

for BASH, I will just post it here.
``` source <(kubectl completion bash) # set up autocomplete in bash into the current shell, bash-completion package should be installed first.
echo "source <(kubectl completion bash)" >> ~/.bashrc # add autocomplete permanently to your bash shell.
alias k=kubectl
complete -o default -F __start_kubectl k
```

## Check how many nodes you have
```
kubectl get nodes
```

## Check how many pods you have in a certain namespace
```
kubectl get hpa -n <NAMESPACE_NAME>
```

### Set autoscale rules for HPA
```
kubectl -n <NAMESPACE_NAME> autoscale deployment <RESOURCE_NAME> --name=??? --min=??? ==max=???