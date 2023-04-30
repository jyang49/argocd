## create app

argocd app create app-1 \
  --repo https://github.com/jyang49/argocd.git \
  --revision main \
  --path examples/basic/01-pod/manifest \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace testing-argocd \
  --sync-option CreateNamespace=true

## list app

argocd app list

# sync app

argocd app sync app-1

## delete app

argocd app delete app-1
