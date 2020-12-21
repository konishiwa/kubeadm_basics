# Create Pod

Sample K8 pod creation with the following attributes:

### Pod Attributes:

- Container Image: nginx
- ContainerPort: 80
- Namespace: web

### Container Commands:

- Set command to nginx
    - Run in quiet mode

    ```bash
    nginx -g daemon off; -q
    ```

### Test Container:

- Find pod:

```bash
kubectl get pods -n web 
```

- Get pod information:

```bash
kubectl describe pod nginx -n web
```