# Openshift Helm Nginx --debug --dry-run template & lint

...

Instalar my-nginx con las opciones de helm: --debug --dry-run

```helm install my-nginx --debug --dry-run bitnami-nginx > my-nginx.yaml```

Revisar el archivo generado:

```vim my-nginx.yaml```

Para ver la generacion de templates:

```helm template bitnami-nginx```

Para validar por algun error en estructura de helm:

```helm lint bitnami-nginx```



