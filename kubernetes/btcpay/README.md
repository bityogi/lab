# Building a BTCPayServer deployment in Kubernetes from scratch

[Reference](https://docs.btcpayserver.org/Deployment/ManualDeployment/)

Structure:

kubernetes/
btcpay/
deployments/
bitcoind.yaml
lnd.yaml
rtl.yaml
nbxplorer.yaml
btcpayserver.yaml
db.yaml
services/
bitcoind.yaml
nbxplorer.yaml
btcpayserver.yaml
db.yaml
config/
network-configmap.yaml
secrets/
rpc-secrets.yaml
namespaces/
btcpay-ns.yaml
