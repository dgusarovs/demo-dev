Structure: <br />
└── demo-dev # root folder <br />
├── applications # apps folder <br />
│ ├── app1.yaml  # 1st app <br />
│ └── app2.yaml  # 2nd app <br />
└── root.yaml    # main app <br />
└── HelmCharts # all Helm Charts <br />
└── terraform # optional task <br />
└── ChartTest1  # chart for bonus task <br />
├── Chart.yaml  # chart file <br />
├── templates   # templates for deploying apps <br />
├── values_dev.yaml # DEV Values <br />
└── values.yaml # default Values <br />

To deploy apps: <br />
>kubectl apply -f root.yaml <br />

To deploy helmchart: <br />
>argocd app create kube-state-metrics   --repo https://github.com/dgusarovs/demo-dev.git   --path HelmCharts/ChartTest1   --dest-server https://kubernetes.default.svc   --dest-namespace kube-state-metrics   --sync-option CreateNamespace=true   --parameter namespace=kube-state-metrics   --values values_dev.yaml --sync-policy automated
