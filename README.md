# ZWS Platform GitOps

Helm values for each app are defined in `helm/<app-namespace>/<app-name>/values[-ENV].yaml`.

## Using direct Argocd ApplicationSet

    kubectl apply -f appset/dev.yaml

## Using the **environment** meta chart

Set up a list of applications defined in environment/values-ENV.yaml

    kubectl apply -f local-environment.yaml

    kubectl apply -f dev-environment.yaml

## Install Local ArgoCD

    kubectl kustomize --load-restrictor LoadRestrictionsNone argocd-local | k apply -f -
