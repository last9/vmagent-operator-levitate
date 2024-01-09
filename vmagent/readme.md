## Step 4: Install VMAgent

### Prerequisites:

Ensure you have installed the VM Operator as per [Step 3](..%2Foperator%2Freadme.md)

You will need to obtain your Levitate cluster's Remote Write URL and its
credentials.

[Here](https://docs.last9.io/docs/levitate-onboard) is a quick way to create your cluster and obtain your
credentials

Run the below command to list all the placeholder values in this file [vmagent.yaml](vmagent.yaml)

```bash
$ cat ./vmagent.yaml | grep -n "Todo"
# Output
11:  levitate_cluster_username: "<levitate_cluster_username>" # Todo: append levitate cluster username
12:  levitate_cluster_password: "<levitate_cluster_password>" # Todo: append levitate cluster password
31:    via_cluster: <via_cluster> # Todo: add a relevant cluster name. e.g: k8s cluster name
33:    - url: <levitate_remote_write_url> # Todo: append levitate remote write URL
55:            storage: 20Gi # Todo: Default is 20Gi. Scale up after you have provisioned more if you need more
58:# Todo: Below configs need to be enabled depending upon your affinity towards nodegroups.
59:# Todo: Ensure that the below selector terms and tolerations are exactly same as the metadata of the nodegroups itself.
```

Proceed to installation once you have replaced the placeholder values with actual values.

### Installation:

1. Install VMAgent in the `last9-monitoring` namespace using `kubectl`:

    ```bash
    $ kubectl apply -f ./vmagent.yaml -n last9-monitoring
    ```

2. Verify the status of the vmagent and ensure that it's running:

    ```bash
    $ kubectl get pods -n last9-monitoring -l "last9_monitoring_agent=vmagent"
    # Output
    NAME                            READY   STATUS    RESTARTS   AGE
    vmagent-demo-6785f7d7b9-zpbv6   2/2     Running   0          72s
    ```
