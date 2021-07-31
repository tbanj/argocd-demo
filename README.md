apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: nginx-alpine
  namespace: argocd
spec:
  destination:
    namespace: default
    server: https://kubernetes.default.svc
  project: default
  source:
    # path to the folder with the YAML manifests
    path: exercises/manifests
    repoURL: https://github.com/tbanj/argocd-demo 
    targetRevision: HEAD
  # Sync policy
  syncPolicy: {}