# Create Pod

Sample K8 pod creation with the following attributes:

### Pod Attributes:

- Pod Name: my-pod 
- Labels: app:my app
- Container Image: busybox
- Name: myapp-container
- Namespace: my-ns

### Container Commands:

- Set command to busybox
    - Run in quiet mode

    ```bash
    sh -c Hello Kubernetes! && sleep 3600
    ```

### Test Container:

- Find pod:

```bash
kubectl get pods
```

- Get pod information:

```bash
kubectl describe pod busybox -n web
```