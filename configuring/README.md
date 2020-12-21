# Create Pod

Sample K8 pod configuration with the following attributes:

### Current Container Attributes:

- Container Image: linuxacademycontent/candy-service:1
- Container Configuration Data
    - Data Location: /etc/candy-service/candy.cfg
    - ConfigMap: candy-service-config
        - Provide to container as mounted volume 
```bash
candy.peppermint.power=100000000
candy.nougat-armor.strength=10
```
- The container will need to run with the file system group with the id 2000. You will need to set this using the securityContext.
- Resource Requests:
    - 64MiB of memory
    - 250m CPU 
- Resource Limits: 
    - 128MiB of memory
    - 500m CPU
- The container needs access to a database password in order to authenticate with a backend database server. 
    - The password is Kub3rn3t3sRul3s!
    - Passed to the container as an environment variable called DB_PASSWORD.
- The container will need to access the Kubernetes API using the service account candy-svc.

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