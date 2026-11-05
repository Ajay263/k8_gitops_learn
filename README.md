# k8_gitops_learn

JDIV-Iqn2p8-j4As


JDIV-Iqn2p8-j4As


admin


###








#  create Application  and add Repo

```
argocd app create nginx-demo \
  --repo https://github.com/Ajay263/k8_gitops_learn \
  --path argocd-demo-app/nginx-demo \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace default
```


`
argocd-demo → nginx-demo (your app name)

YOUR-USERNAME/argocd-demo.git → Ajay263/k8_gitops_learn (your repo)

--path . → --path argocd-demo-app/nginx-demo (your folder, not the root)

`


```
argocd app sync nginx-demo
```





port forward argocd

```

kubectl port-forward svc/argocd-server -n argocd 8080:443

```



```
kubectl -n argocd get secret argocd-initial-admin-secret -o
jsonpath="{.data.password}" | base64 -d

```