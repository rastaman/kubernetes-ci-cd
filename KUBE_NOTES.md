# K8S notes

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

## References

Access k8s on other server, configure cluster, configuring RBAC :

- [Configure Access to Multiple Clusters - Kubernetes](https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/)
- [networking - how to access local kubernetes minikube dashboard remotely - Stack Overflow](https://stackoverflow.com/questions/47173463/how-to-access-local-kubernetes-minikube-dashboard-remotely)
- [How to set up Kubernetes on Windows 10 with Docker for Windows and run ASP.NET Core - Scott Hanselman](https://www.hanselman.com/blog/HowToSetUpKubernetesOnWindows10WithDockerForWindowsAndRunASPNETCore.aspx)
- [How to sign in kubernetes dashboard? - Stack Overflow](https://stackoverflow.com/questions/46664104/how-to-sign-in-kubernetes-dashboard)
- [Configure RBAC in your Kubernetes Cluster](https://docs.bitnami.com/kubernetes/how-to/configure-rbac-in-your-kubernetes-cluster/)
- Dashboard [Access control - kubernetes/dashboard Wiki](https://github.com/kubernetes/dashboard/wiki/Access-control#basic)

# Articles and tutorials

- [Set Up a CI/CD Pipeline with Kubernetes Part 1: Overview](https://www.linux.com/blog/learn/chapter/Intro-to-Kubernetes/2017/5/set-cicd-pipeline-kubernetes-part-1-overview)