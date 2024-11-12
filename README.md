# Openshift Helm Nginx

Verificar las versiones:

```oc  get clusterversion```

```helm version```

Agregar repositorios

```helm repo add bitnami https://charts.bitnami.com/bitnami```

```helm repo add redhat-charts https://redhat-developer.github.io/redhat-helm-charts```

```helm repo add openshift-helm-charts https://charts.openshift.io/```

Ver el listado de los repositorios 

```helm repo list```

Ver el listado de los paquetes:

```helm search repo bitnami```

```helm search repo redhat-chart```

```helm search repo openshift-helm-charts```

Buscar app nginx

```helm search repo bitnami/nginx```

Crear archivos de helm para solución: my-nginx

```helm create bitnami-nginx```

Revisar que la estrucura esta ok:

```tree bitnami-nginx```

Editar archivo values.yaml:

```vim bitnami-nginx/values.yaml```

Modificar archivo:

```repository: nginx   --->   repository: bitnami/nginx```

```port:80   --->   port:8080```

Instalar estructura:

```helm install my-nginx bitnami-nginx```

ó:

```helm install my-nginx bitnami-nginx ```

Revisar que este instalado:

```helm ls```

```helm list -a```

Generar ruta para que podamos llegar a el desde internet:

```oc expose svc/my-nginx-bitnami-nginx```

Validar que la ruta se genero correctamente:

```oc get routes```

Desinstalar app:

```helm uninstall my-nginx```

No olvides eliminar la ruta:

```oc delete route my-nginx-bitnami-nginx```



