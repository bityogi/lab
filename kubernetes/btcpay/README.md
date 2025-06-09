# Building a BTCPayServer deployment in Kubernetes from scratch

[Reference](https://docs.btcpayserver.org/Deployment/ManualDeployment/)

## Deployment

- Namespace
  `kubectl apply -f kubernetes/btcpay/namespaces/`

- Secrets
  `kubectl apply -f kubernetes/btcpay/secrets/`

- ConfigMaps
  `kubectl apply -f kubernetes/btcpay/config/`

- PVCs
  `kubectl apply -f kubernetes/btcpay/pvc/`

- Deployments
  `kubectl apply -f kubernetes/btcpay/deployments/`

Lets run the Deployments separately one by one.

- After the lnd deployment has been applied,

After lnd is run for the first time you will create a wallet.
`kubectl exec -it -n btcpay {lnd-pod-name} -- lncli --network=testnet create`

Password: password
Seed: ---------------BEGIN LND CIPHER SEED---------------

1.  absent 2. impose 3. review 4. abuse
2.  muffin 6. toy 7. opera 8. umbrella
3.  lecture 10. ladder 11. double 12. february
4.  lounge 14. holiday 15. icon 16. puppy
5.  step 18. cave 19. surround 20. scare
6.  crawl 22. metal 23. chalk 24. travel
    ---------------END LND CIPHER SEED-----------------

Don't worry, this is just testnet so there isn't any real money here folks!

- Services
  `kubectl apply -f kubernetes/btcpay/services/`

- Ingress
  `kubectl apply -f kubernetes/btcpay/ingress/`
