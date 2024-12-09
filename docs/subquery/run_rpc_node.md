# Running Autonity RPC node for Subquery Network RPC Gateway 

### Run RPC on the some machine where installed Subquery indexer


1. Download [docker-compose.yaml](https://raw.githubusercontent.com/web3cdnservices/autonity-validator-toolkit/refs/heads/main/docs/subquery/docker-compose-public-rpc.yml) description file.
   ```
   mkdir -p /usr/src/autonity_rpc_node
   cd /usr/src/autonity_rpc_node
   wget -O docker-compose.yaml https://raw.githubusercontent.com/web3cdnservices/autonity-validator-toolkit/refs/heads/main/docs/subquery/docker-compose-public-rpc.yml
   ```

   
2.  Run node.
   
    If `docker-compose` command available, run
    ```
    docker-compose up -d
    ```

    Else if you use latest docker, you can user `docker compose` command (docker now integrae compose)
    ```
    docker compose up -d
    ```
