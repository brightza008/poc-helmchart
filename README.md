# poc-helmchart
for poc-helmchart on  minikube

```
helm install my-cherry-chart buildchart/ --values buildchart/values-global.yaml --values buildchart/values-dev.yaml
helm uninstall my-cherry-chart

```
```
$ export POD_NAME=$(kubectl get pods -l "app.kubernetes.io/name=buildchart,app.kubernetes.io/instance=my-cherry-chart" -o jsonpath="{.items[0].metadata.name}")

$ echo "Visit http://127.0.0.1:8080 to use your application"
Visit http://127.0.0.1:8080 to use your application

$ kubectl port-forward $POD_NAME 8080:80
Forwarding from 127.0.0.1:8080 -> 80
Forwarding from [::1]:8080 -> 80
```