# lab-openshift-config

Manifestos Kustomize do laboratório final de OpenShift (curso 200DEV), lidos pelo OpenShift GitOps (Argo CD).

## Estrutura

- `base/`: Deployment `lab-app` (porta 8080, label `app=lab-app`), Service `lab-app` e Route `lab-app`.
- `overlays/dev/`: aponta para `base/` e define a imagem do ambiente de desenvolvimento.
- `overlays/prod/`: mesma estrutura, para o ambiente de produção.

## Antes de usar

Em `overlays/dev/kustomization.yaml` e `overlays/prod/kustomization.yaml`, troque `<REGISTRY>/<usuario>/lab-app` pelo registry e pelo seu usuário, e ajuste o `newTag` conforme a imagem gerada pela pipeline.

Para validar sem o cluster:

```
kubectl kustomize overlays/dev
kubectl kustomize overlays/prod
```

Faça fork deste repositório antes do Bloco 8 do laboratório.
