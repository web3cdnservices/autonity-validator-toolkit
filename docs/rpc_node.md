# Rpc node run & sign

https://game.autonity.org/awards/register-node.html


## Generate keys
```
git pull
./tools/import_rpc_nodekey
```

## `SIGNATURE OF MESSAGE "PUBLIC RPC"`
```
aut account sign-message -k /root/.autonity/keystore/nodekey_rpc  "public rpc"
```
## `ENODE OF YOUR RPC NODE`
```
aut node info -r http://autonity_rpc:8545  | jq -r ".admin_enode"
```

## `RPC NODE ENDPOINT`
http://Your ip:8945/
