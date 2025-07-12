**🚀 Argo CD Multi-App Helm Deployment with ApplicationSet**

This repository demonstrates how to deploy multiple applications dynamically using Argo CD's ApplicationSet controller combined with a shared Helm chart.

**It supports:**

Folder-based application discovery

Helm chart reusability

Automatic namespace creation

Syncing on Git changes


**🔁 How It Works**

The ApplicationSet controller uses the git.directory generator to scan apps/*

For every folder (app1, app2, app3), it creates an Argo CD Application

Each app gets deployed using the shared Helm chart and its own values.yaml

Apps are deployed in separate namespaces

Taints in EKS are handled via tolerations

**⚙️ Key Concepts**

Git-based app discovery using folder names

Namespace-per-app pattern

Helm chart reuse for multiple applications

Automatic deployment via Argo CD ApplicationSet

Tolerations used for EKS node scheduling (especially with Auto mode)

**🚀 Deployment Steps**

✅ Connect this repo to Argo CD (Settings → Repositories)

✅ Apply applicationset.yaml under argocd/

✅ Argo CD will automatically create and sync app1, app2, app3 using Helm

✅ Monitor each application in Argo CD UI under "Applications"

**🛠️ Troubleshooting**

❌ Application not showing up

Make sure the path in directories: matches the actual folder structure

Ensure values.yaml is present for each app folder

❌ FailedScheduling error

Nodes in EKS Auto mode are often tainted

Add tolerations: to your Helm deployment templates to handle taints such as CriticalAddonsOnly and karpenter.sh/disrupted

**🧪 Future Improvements**

Parameterize tolerations via values.yaml

Add Kustomize overlays for prod/stage/dev

Add Prometheus/Grafana setup for monitoring

**👌 Credits**

Built with 💙 using:

Argo CD

Helm

AWS EKS

**📬 Reach Out**

Feel free to fork, open issues, or connect with me on LinkedIn (https://www.linkedin.com/in/aditya-mishra-a0315b154/)!

#GitOps #ArgoCD #Helm #Kubernetes #DevOps #ApplicationSet #EKS #CloudNative
