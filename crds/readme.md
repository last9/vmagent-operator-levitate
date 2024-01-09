## Step 2: Install Custom Resource Definitions (CRDs)

### Prerequisites:
Ensure you have completed [Step 1](..%2Freadme.md)

### Installation:

1. Install the CRDs using `kubectl`:

    ```bash
    $ kubectl apply -f ./crd.yaml
    ```

2. Verify that the CRDs are successfully installed:

    ```bash
    $ kubectl get crd --sort-by=.metadata.creationTimestamp
    # Output
   NAME                                                         CREATED AT
   vmagents.operator.victoriametrics.com                        2023-12-26T12:02:48Z
   vmnodescrapes.operator.victoriametrics.com                   2023-12-26T12:02:49Z
   vmservicescrapes.operator.victoriametrics.com                2023-12-26T12:02:50Z
   vmprobes.operator.victoriametrics.com                        2023-12-26T12:02:50Z
   vmpodscrapes.operator.victoriametrics.com                    2023-12-26T12:02:50Z
   vmstaticscrapes.operator.victoriametrics.com                 2023-12-26T12:02:51Z
    ```

   You should see the names of the installed CRDs in the output.
