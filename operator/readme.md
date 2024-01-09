## Step 3: Install VM Operator

### Prerequisites:
Ensure you have all necessary CRDs installed as per [Step 2](..%2Fcrds%2Freadme.md)

### Installation:

1. Install the operator and rbac using `kubectl`:

    ```bash
    $ kubectl apply -f ./manager.yaml -f rbac.yaml
    ```

2. Verify the status of the operator:

    ```bash
    $ kubectl get pods -n monitoring-system
    # Output
    NAME                           READY   STATUS    RESTARTS   AGE
    vm-operator-667dfbff55-cbvkf   1/1     Running   0          101s          2023-12-26T12:02:51Z
    ```

   You should see the vmoperator pod in running status.
