# K8S notes

Trying to access the dashboard from my external host...

```sh
C:\>kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/alternative/kubernetes-dashboard.yaml
serviceaccount "kubernetes-dashboard" created
role.rbac.authorization.k8s.io "kubernetes-dashboard-minimal" created
rolebinding.rbac.authorization.k8s.io "kubernetes-dashboard-minimal" created
deployment.apps "kubernetes-dashboard" created
service "kubernetes-dashboard" created

C:\>kubectl create -f https://raw.githubusercontent.com/kubernetes/heapster/master/deploy/kube-config/influxdb/influxdb.yaml
deployment.extensions "monitoring-influxdb" created
service "monitoring-influxdb" created

C:\>kubectl create -f https://raw.githubusercontent.com/kubernetes/heapster/master/deploy/kube-config/influxdb/heapster.yaml
serviceaccount "heapster" created
deployment.extensions "heapster" created
service "heapster" created

C:\>kubectl create -f https://raw.githubusercontent.com/kubernetes/heapster/master/deploy/kube-config/influxdb/grafana.yaml
deployment.extensions "monitoring-grafana" created
service "monitoring-grafana" created

C:\>kubectl proxy --address=192.168.y.z
Starting to serve on 192.168.y.z:8001
```

From the external host :

```sh
$ kubectl get pods --all-namespaces
NAMESPACE     NAME                                         READY     STATUS    RESTARTS   AGE
default       nginx-768979984b-s6dnf                       1/1       Running   0          1d
docker        compose-7447646cf5-k8sjv                     1/1       Running   0          1d
docker        compose-api-6fbc44c575-s57p6                 1/1       Running   1          1d
kube-system   etcd-docker-for-desktop                      1/1       Running   0          1d
kube-system   heapster-7ff8d6bf9f-8bdp6                    1/1       Running   0          1d
kube-system   kube-apiserver-docker-for-desktop            1/1       Running   0          1d
kube-system   kube-controller-manager-docker-for-desktop   1/1       Running   0          1d
kube-system   kube-dns-86f4d74b45-h8qrp                    3/3       Running   1          1d
kube-system   kube-proxy-d4tgv                             1/1       Running   0          1d
kube-system   kube-scheduler-docker-for-desktop            1/1       Running   0          1d
kube-system   kubernetes-dashboard-7b9c7bc8c9-bpsp7        1/1       Running   0          2m
kube-system   monitoring-grafana-68b57d754-wzrcg           1/1       Running   0          1d
kube-system   monitoring-influxdb-cc95575b9-lhgc6          1/1       Running   0          1d
```

## References

Access k8s on other server, configure cluster, configuring RBAC :

- [Configure Access to Multiple Clusters - Kubernetes](https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/)
- [networking - how to access local kubernetes minikube dashboard remotely - Stack Overflow](https://stackoverflow.com/questions/47173463/how-to-access-local-kubernetes-minikube-dashboard-remotely)
- [How to set up Kubernetes on Windows 10 with Docker for Windows and run ASP.NET Core - Scott Hanselman](https://www.hanselman.com/blog/HowToSetUpKubernetesOnWindows10WithDockerForWindowsAndRunASPNETCore.aspx)
- [How to sign in kubernetes dashboard? - Stack Overflow](https://stackoverflow.com/questions/46664104/how-to-sign-in-kubernetes-dashboard)
- [Configure RBAC in your Kubernetes Cluster](https://docs.bitnami.com/kubernetes/how-to/configure-rbac-in-your-kubernetes-cluster/)
- Dashboard [Access control - kubernetes/dashboard Wiki](https://github.com/kubernetes/dashboard/wiki/Access-control#basic)
- [Added Addon Authn Pattern proposal by erictune - Pull Request #29714 - kubernetes/kubernetes](https://github.com/kubernetes/kubernetes/pull/29714)

- [kubectl Cheat Sheet - Kubernetes](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [JSONPath Support - Kubernetes](https://kubernetes.io/docs/reference/kubectl/jsonpath/)

- [Namespaces - Kubernetes](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/)

# Articles and tutorials

- [Set Up a CI/CD Pipeline with Kubernetes Part 1: Overview](https://www.linux.com/blog/learn/chapter/Intro-to-Kubernetes/2017/5/set-cicd-pipeline-kubernetes-part-1-overview)
