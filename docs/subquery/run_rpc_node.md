# Running Autonity RPC node for Subquery Network RPC Gateway 




1. ### Download [docker-compose.yaml](https://raw.githubusercontent.com/web3cdnservices/autonity-validator-toolkit/refs/heads/main/docs/subquery/docker-compose-public-rpc.yml) description file.
   ```
   mkdir -p /usr/src/autonity_rpc_node
   cd /usr/src/autonity_rpc_node
   wget -O docker-compose.yaml https://raw.githubusercontent.com/web3cdnservices/autonity-validator-toolkit/refs/heads/main/docs/subquery/docker-compose-public-rpc.yml
   ```

   
2.  ### Run node.
   
    If `docker-compose` command available, run
    ```
    docker-compose up -d
    ```

    Else if you use latest docker, you can user `docker compose` command (docker now integrae compose)
    ```
    docker compose up -d
    ```

3. ### Connect Autonity RPC to Subquery Indexer

   #### 3.1.  Add new project with cid: `QmSXV8pkxKufQNGdaJ2N15t4cCta4iYWL7QXdLvtjEaS48`

   #### 3.2.  Fill fields with values:

- HTTP Endpoint:
  ```
  http://autonity_rpc:8545
  ```
- WebSocket Endpoint:
  ```
  ws://autonity_rpc:8546
  ```
- Metrics Endpoint:
  ```
  http://autonity_rpc:6064/debug/metrics
  ```
   
   ![image](https://github.com/user-attachments/assets/4ca55bb5-92dc-4b97-ab0d-2922b98d72cf)

4. Set PAYG price <=1.5 SQT / 3 Days.
