## Incredible squating AVS packaging

### How to use with eigenlayer-cli

#### Register operator 
```
eigenlayer operator register --configuration-file operator-config.yaml
```
Make sure you have some ETH as this is an on-chain transaction

#### Install AVS
```
eigenlayer install https://github.com/shrimalmadhur/incredible-squaring-pkg
```
Follow the prompt to fill in the required details.

If you have packaging directory cloned locally and want to install using that then
```
eigenlayer local-install <path-to>/incredible-squaring-pkg --profile testnet
```

### Delegate some token to operator
```
eigenlayer plugin --host --no-rm-image --volume /root/operator_keys/demo.ecdsa.key.json:/operator_keys/ecdsa_key.json --volume /root/avs_config.yaml:/app/avs_config.yaml incredible-squaring-avs-default --operation-type deposit --strategy-addr 0x7a2088a1bFc9d81c55368AE168C2C02570cB814F --ecdsa-key-password=
```

### Opt-in to this AVS
```
eigenlayer plugin --host --no-rm-image --volume /root/operator_keys/demo.ecdsa.key.json:/operator_keys/ecdsa_key.json --volume /root/operator_keys/demo.bls.key.json:/operator_keys/bls_key.json --volume /root/avs_config.yaml:/app/avs_config.yaml incredible-squaring-avs-default --operation-type opt-in --ecdsa-key-password= --bls-key-password=
```

This will register your BLS key and opt into this AVS

####Run AVS offchain software
Get the AVS instance id from the following command
```
eigenlayer ls
```

Run the software using
```
eigenlayer run <instance-id>
```

### Stopping offchain software
```
eigenlayer stop <instance-id>
```

### Uninstalling offchain software
```
eigenlayer uninstall <instance-id>
```