## Incredible squating AVS packaging

### How to use with eigenlayer-cli

#### Register operator 
```
eigenlayer operator register --configuration-file operator-config.yaml
```
Make sure you have some ETH as this is an on-chain transaction

#### Install AVS
```
eigenlayer install https://github.com/Layr-Labs/incredible-squaring-pkg
```
Follow the prompt to fill in the required details.

If you have packaging directory cloned locally and want to install using that then
```
eigenlayer local-install <path-to>/incredible-squaring-pkg --profile testnet
```

#### Opt-in to this AVS
```
eigenlayer plugin --host --no-rm-image --volume <path-to-ecdsa-key-file>:/operator_keys/ecdsa_key.json --volume <path-to-bls-key-file>:/operator_keys/bls_key.json --volume <path-to-avs-config-file>:/app/avs_config.yaml incredible-squaring-pkg-default
```

This will register your BLS key and opt into this AVS

#### Run AVS offchain software
Get the AVS instance id from the following command
```
eigenlayer ls
```

Run the software using
```
eigenlayer run <instance-id>
```

#### Stopping offchain software
```
eigenlayer stop <instance-id>
```

#### Uninstalling offchain software
```
eigenlayer uninstall <instance-id>
```