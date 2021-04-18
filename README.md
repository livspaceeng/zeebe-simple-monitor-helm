# [zeebe-simple-monitor-helm](https://github.com/livspaceeng/zeebe-simple-monitor-helm)

Helm chart to host Zeebe Simple Monitor app on Kubernetes cluster
> **Latest Chart version: 0.6.0**

### Deployment Steps
- Clone [zeebe-simple-monitor-fork](https://github.com/livspaceeng/zeebe-simple-monitor) repo. Make the changes, and push the required changes, to master branch.
- [Dockerfile](https://github.com/livspaceeng/zeebe-simple-monitor/blob/master/Dockerfile) will trigger a multi-stage build, to build the source-code and generate Docker image, on [Docker hub](https://hub.docker.com/repository/docker/livspaceeng/zeebe-simple-monitor).
- Clone these 2 repo in your home (**~**) directory:
  + [zeebe-simple-monitor helm repo](https://github.com/livspaceeng/zeebe-simple-monitor-helm)
  + [helm-chart repo](https://github.com/livspaceeng/helm-charts)
- Make any required changes to [zeebe-simple-monitor-helm](https://github.com/livspaceeng/zeebe-simple-monitor-helm) repo.
- Update the **appVersion** in [Chart.yaml](./zeebe-simple-monitor/Chart.yaml) to point to the current [zeebe-simple-monitor version](https://github.com/livspaceeng/zeebe-simple-monitor/blob/master/pom.xml) (*Just to be aware of the current version being used*).
- Upgrade the **version** in [Chart.yaml](./zeebe-simple-monitor/Chart.yaml), and push to this repo.
- Run the below commands from terminal (*inside ~/helm-charts directory*):
  + `> helm package ../zeebe-simple-monitor-helm/zeebe-simple-monitor`
  + `> helm repo index --merge index.yaml --url https://charts.livspace.com .`
  + `> git commit`
  + `> git push origin`
- Use the **version** from [Chart.yaml](./zeebe-simple-monitor/Chart.yaml) and update it in requirements.yaml.

That's it! :)
