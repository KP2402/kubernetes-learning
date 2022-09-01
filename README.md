# kubernetes-learning
Learning and hands-on on Kubernetes

## Setting up keyloak

```kubectl create -f https://raw.githubusercontent.com/keycloak/keycloak-quickstarts/latest/kubernetes-examples/keycloak.yaml -n keycloak-ns
```

```KEYCLOAK_URL=http://$(minikube ip):$(kubectl get services/keycloak -o go-template='{{(index .spec.ports 0).nodePort}}' -n keycloak-ns) &&
echo "" &&
echo "Keycloak:                 $KEYCLOAK_URL" &&
echo "Keycloak Admin Console:   $KEYCLOAK_URL/admin" &&
echo "Keycloak Account Console: $KEYCLOAK_URL/realms/myrealm/account" &&
echo ""
```

# Run using minikube service tunnel
```minikube service keycloak -n keycloak ns --url
```

# Important reference url
https://www.keycloak.org/docs/latest/securing_apps/#redirect-uris