# Demo:  Application monitoring with Prometheus / Grafana

Monitor a application providing metrics (/metrics url).

The monitored application is the [StockQuote](https://github.com/jtarte/stockquote) application. The Appsody stack used to generate the app includes app-metrics. This library instruments the application and provides metrics.

The scripts in this repo are :
* service_monitor.yaml : the definition of the scrapping of StockQuote app.
* service_account: the service account for prometheus instance
* prometheus.yaml:  the prometheus instance.
* grafana_datasource.yaml: the datasource used by Grafana to get Prometheus information.
* grafana.yaml: the Grafana instance.
* dashboard.yaml. the dashboard for the demo.

If you have already a prometheus/ Grafana instances available, the two files that you have to use is the service_monitor.yaml and dashboard.yaml

Warning: the `ServiceMonitor` should define a label to be identified by prometheus. here it is `k8s-app: stockquote-monitor`. The Prometheus instance of our example is looking for a key : `k8s-app`.

Warning: the namespace used for this sample is : prometheus-operator. 

ref: https://kabanero.io/guides/app-monitoring-ocp4.2/
