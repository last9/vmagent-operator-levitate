## Step 5: Install VMServiceScrape (i.e ServiceMonitor and PodMonitor)

### Prerequisites:

Ensure you have installed the VMAgent as per [Step 4](..%2Fvmagent%2Freadme.md)

**Caveats**

VMServiceScrape works similar to Prometheus Operator's ServiceMonitor and PodMonitor where you can define scrape
selectors to do service and pod discovery.

In this file [vmservicescrape.yaml](vmservicescrape.yaml) you can override default scrape selectors to suit your
requirements. By default this assumes the default labels that are applied to the exporter as part of their
installations.

Below is the generic command to find you the labels of your K8s Services.

```bash
$ kubectl get services -n <namespace> <service-name> -o jsonpath='{.metadata.labels}'
```

Once, you have inspected the labels for the services that you chose to scrape, you can then proceed to modify this
file [vmservicescrape.yaml](vmservicescrape.yaml) and match the scrape selector labels with the labels of your services.

Another caveat to note here is to ensure that the namespaces are also declared correctly for the scrape selectors to correctly perform service discovery.

This file also includes scrape configs for Common Exporters such as Kafka, Redis, Node, RabbitMQ, Prometheus
Pushgateway etc.

Run this command to list all the `Todo` comments which will guide you to customize this file [vmservicescrape.yaml](vmservicescrape.yaml) as required.
```bash
$ cat ./vmservicescrape.yaml | grep -n "Todo"
# Output
48:    matchNames: [ "kube-system" ] # Todo: append namespaces here
63:    matchNames: [ "kube-system" ] # Todo: append namespaces here
86:# Todo: Uncomment this if you have custom application enabled svcs running and you want to scrape them
97:#    matchNames: [ ] # Todo: Append more namespaces here
105:#      app: "" # Todo: Append app name label here
107:# Todo: Uncomment this if you have node exporters svcs running and you want to scrape them
118:#    matchNames: [ ] # Todo: Append more namespaces here
129:# Todo: Uncomment this if you have rabbitMQ exporters svcs running and you want to scrape them
140:#    matchNames: [  ] # Todo: Append more namespaces here
151:# Todo: Uncomment this if you have kafka exporters svcs running and you want to scrape them
162:#    matchNames: [  ] # Todo: Append more namespaces here
173:# Todo: Uncomment this if you have redis exporters svcs running and you want to scrape them
184:#    matchNames: [ ] # Todo: Append more namespaces here
195:# Todo: Uncomment this if you have pushgateway svcs running and you want to scrape them
206:#    matchNames: [ ] # Todo: Append more namespaces here
```

### Installation:

Install VMServiceScrape using `kubectl`:

 ```bash
 $ kubectl apply -f ./vmservicescrape.yaml -n last9-monitoring
 # Output
vmservicescrape.operator.victoriametrics.com/last9-vmservicescrape-vmagent-01 created
vmservicescrape.operator.victoriametrics.com/last9-servicescrape-k8s-01 created
vmservicescrape.operator.victoriametrics.com/last9-servicescrape-metrics-server-01 created
 ```
