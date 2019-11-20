# [zeebe-simple-monitor-helm-chart](https://github.com/livspaceeng/zeebe-simple-monitor)

Helm chart to host Zeebe Simple Monitor app on Kubernetes cluster
> Latest release: 0.2.0

### Deployment Steps
- Clone [zeebe-simple-monitor-fork](https://github.com/strawhat5/zeebe-simple-monitor) repo and push the required changes to master branch.
- It will trigger an automated build on [Docker hub](https://hub.docker.com/repository/docker/livspaceeng/zeebe-simple-monitor).
- Clone these 2 repo in your home (**~**) folder:
  + [zeebe-simple-monitor helm repo](https://github.com/livspaceeng/zeebe-simple-monitor)
  + [helm-chart repo](https://github.com/livspaceeng/helm-charts)
- Make any required changes to [zeebe-simple-monitor helm repo](https://github.com/livspaceeng/zeebe-simple-monitor) repo.
- Update the **appVersion** in [Chart.yaml](./Chart.yaml) to point to the current [zeebe-simple-monitor version](https://github.com/strawhat5/zeebe-simple-monitor/blob/master/pom.xml) (*Just to be aware of the current version being used*).
- Upgrade the **version** in [Chart.yaml](./Chart.yaml).
- Run in ~/helm-charts folder:
  + helm package ../zeebe-simple-monitor
  + helm repo index --merge index.yaml --url https://charts.livspace.com .
- Use the **version** from [Chart.yaml](./Chart.yaml) and update it in [requirements.yaml](https://bitbucket.org/livspaceeng/environment-jx-dev/src/master/env/requirements.yaml).

That's it! ;)
