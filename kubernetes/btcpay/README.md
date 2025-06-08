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

1.  absorb 2. child 3. innocent 4. glimpse
2.  travel 6. hamster 7. element 8. together
3.  hole 10. bean 11. skill 12. razor
4.  one 14. fun 15. relax 16. wool
5.  problem 18. cigar 19. comfort 20. toy
6.  master 22. document 23. grape 24. demise  
    ---------------END LND CIPHER SEED-----------------

Don't worry, this is just testnet so there isn't any real money here folks!

- Services
  `kubectl apply -f kubernetes/btcpay/services/`

- Ingress
  `kubectl apply -f kubernetes/btcpay/ingress/`
