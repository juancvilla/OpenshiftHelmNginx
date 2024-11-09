# Openshift Helm Nginx

Verificar las versiones:

```oc  get clusterversion```

```helm version```

Agregar repositorio bitnami

```helm repo add bitnami https://charts.bitnami.com/bitnami```

Ver que bitnami este en la lista de los repositorios 

```helm repo list```

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



