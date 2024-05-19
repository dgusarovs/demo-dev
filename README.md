Structure:
└── demo-dev # root folder
├── applications # apps folder
│ ├── app1.yaml  # 1st app
│ └── app2.yaml  # 2nd app
└── root.yaml    # main app
└── HelmCharts # All Helm Charts
└── ChartTest1  # chart for bonus task
├── Chart.yaml  # chart file
├── templates   # templates for deploying apps
├── values_dev.yaml # DEV Values
└── values.yaml # Default Values

To deploy apps:
kubectl apply -f root.yaml
To deploy helmchart:
argocd app create kube-state-metrics   --repo https://github.com/dgusarovs/demo-dev.git   --path HelmCharts/ChartTest1   --dest-server https://kubernetes.default.svc   --dest-namespace kube-state-metrics   --sync-option CreateNamespace=true   --parameter namespace=kube-state-metrics   --values values_dev.yaml --sync-policy automated
