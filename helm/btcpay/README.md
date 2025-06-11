# filepath: /btcpay-helm/btcpay-helm/README.md
# BTCPay Helm Chart

This Helm chart deploys BTCPay Server along with its dependencies in a Kubernetes cluster. It includes configurations for Bitcoin, PostgreSQL, LND, NBXplorer, and RTL (Ride The Lightning).

## Prerequisites

- Kubernetes 1.12+
- Helm 3.x
- A running Kubernetes cluster

## Installation

1. **Add the Helm repository (if applicable)**:
   ```bash
   helm repo add <repository-name> <repository-url>
   ```

2. **Install the chart**:
   ```bash
   helm install <release-name> ./btcpay-helm
   ```

3. **Verify the installation**:
   ```bash
   kubectl get all -n <namespace>
   ```

## Configuration

The following table lists the configurable parameters of the BTCPay chart and their default values:

| Parameter                       | Description                                   | Default Value       |
|---------------------------------|-----------------------------------------------|---------------------|
| `bitcoin.network`               | The Bitcoin network to use (mainnet/testnet) | `regtest`           |
| `pvc.bitcoind.storage`          | Storage size for Bitcoin data                 | `10Gi`              |
| `pvc.lnd.storage`               | Storage size for LND data                     | `5Gi`               |
| `pvc.postgres.storage`          | Storage size for PostgreSQL data              | `5Gi`               |
| `btcpayserver.image.tag`        | The image tag for the BTCPay Server          | `1.13.0`            |
| `lnd.image.tag`                 | The image tag for LND                         | `v0.18.0-beta`      |
| `postgres.image.tag`            | The image tag for PostgreSQL                  | `15`                |
| `nbxplorer.image.tag`           | The image tag for NBXplorer                   | `2.5.27`            |
| `rtl.image.tag`                 | The image tag for RTL                         | `0.15.1`            |

## Usage

After installation, you can access the BTCPay Server and RTL web interface using the configured Ingress resources. Make sure to set up your DNS records to point to your Kubernetes cluster.

## Uninstallation

To uninstall the chart, run the following command:
```bash
helm uninstall <release-name> -n <namespace>
```

## Contributing

If you would like to contribute to this chart, please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.