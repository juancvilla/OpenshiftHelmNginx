# Openshift Helm Nginx

Verificar las versiones:

```oc  get clusterversion```

```helm version```

Agregar repositorios

```helm repo add bitnami https://charts.bitnami.com/bitnami```

```helm repo add redhat-charts https://redhat-developer.github.io/redhat-helm-charts```

Ver el listado de los repositorios 

```helm repo list```

Ver el listado de los paquetes:

```helm search repo bitnami```

```helm search repo redhat-chart```

Buscar app nginx

```helm search repo bitnami/nginx```

Instalar my-nginx con helm

```helm install my-nginx bitnami/nginx --set service.type=ClusterIP```

Revisar que este instalado:

```helm ls```

Generar ruta para que podamos llegar a el desde internet:

```oc expose svc/my-nginx```

Validar que la ruta se genero correctamente:

```oc get routes```

Desinstalar app:

```helm uninstall my-nginx```

No olvides eliminar la ruta:

```oc delete route my-nginx```



