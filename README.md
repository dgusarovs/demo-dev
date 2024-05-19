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
