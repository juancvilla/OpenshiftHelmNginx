# Openshift Helm Nginx

...

Instalar my-nginx con helm

```helm install my-nginx bitnami/nginx```

Revisar que este instalado:

```helm ls```

```helm list -a```

Editar algunos archivos:

```vim my-nginx/values.yaml```

Modificar algunos valores:

```replicaCount: 1   --->   replicaCount: 2```

Cada vez que se modifique y tengamos un nuevo release utilizar comando:

```helm upgrade my-nginx bitnami-nginx```

Validar con comando:

```helm list -a```

```oc get pods```

Se puede realizar un rollback con el comando:

```helm rollback my-nginx 1```

Notar que el Rollback no vuelve a la versión antigua, sino que se crea una nueva version, pero con las características del nivel de rollback:

```helm list -a```

```oc get pods```

