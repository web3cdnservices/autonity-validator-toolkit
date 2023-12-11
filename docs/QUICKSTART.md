# Autonity validator node.

## Step One
```
cd /usr/src
git clone https://github.com/web3cdnservices/autonity-validator-toolkit.git
cd autonity-validator-toolkit
./tools/install_requirements_ubuntu.sh && ./tools/generate_env_passwords && ./tools/start_autonity && source ~/.bashrc && ./tools/setup_shell_environment && ./tools/node_add_peers_piccadilly && ./tools/generate_oracle_key && ./tools/generate_account main
```

## Step Two (form 1)
### Open form.(faucet registratuin)  https://game.autonity.org/getting-started/register.html

`Address:`
```
cat .data/.autonity/main.public
```
`Signature:`
```
./tools/validator_create_faucet_signature
```

`wait 5 minutes for token delivery`

### Register validator
1. Run command `register`

```
./tools/validator_register main
```
   
Here your validator id:
![image](https://github.com/web3cdnservices/autonity-validator-toolkit/assets/115787312/1bec3c07-cbea-4cfc-bf6d-f74aae5eb22f)


3. Run command `bound`
   ```
   ./tools/validator_bound_tokens/
   ```
Paste here your validatorId.
& password.

## step Three form confirmation.

### Open form https://game.autonity.org/awards/register-validator.html

- Enode:  
```
aut node info | jq -r ".admin_enode"
```

- Signature of message validator onboarded:
```
./tools/validator_create_validator_conformation_signature
```


### Configure APIs for Oracle. (obrain keys)
