# Autonity Validator Toolkit

### What's in?
 - Autonity validator node with snap mode
 - Autonite Oracle
 - node-exporter
 - grafana
 - prometheus
 - wireguard
 - all official tooling (aut)
   ![grafana_Screenshot_20231208_211600](https://github.com/web3cdnservices/autonity-validator-toolkit/assets/115787312/70d3d281-5b5e-4e02-a075-f0d5b81b32f7)


### Setup
1. #### Clone this repo
   ```
   git clone https://github.com/web3cdnservices/autonity-validator-toolkit.git 
   autonity-validator-toolkit
   ```
   
2. #### Install OS requirements.
   ```
   ./tools/install_requirements_ubuntu.sh
   ```
   Script will install docker, docker-compose.

3. #### Configure keys.

  Copy configuration file
   ```
   cp .env.default .env
   ```
  Open in editor and setup configuration.
  ```
nano .env
  ```
   # Description of `.env` fields:

   ### `NETWORK_NAME="bakerloo"`
     - Network name. Now available bakerloo OR piccadilly
   
   ### `ORACLE_KEY_PASSWD="TESTPASSWORD"`
      - Password for Oracle wallet (generation later with aut command)
   
   ### `PROMETHEUS_METRICS_TOKEN="REPLACE_ME"`
      - Write any symbols. this internal key.
   
   ### `GRAFANA_ADMIN_PASSWORD="REPLACE_ME"`
      - Your password for Grafana. Use any symbols. (login admin)
      
   ### `DOCKER_SUBNET_MASK="172.29.13.0"`
      - Keep unchanged (internal config. Local network for WG & docker)
      
   ### `WIREGUARD_PORT=816`
      - Wireguard server port. Keep as is.
      
   ### `WIREGUARD_SUBNET="10.253.1.0"`
      - Keep unchanged (internal config. Local network for WG & docker)
      
   ### `ORACLE_UTC_FILE=""`
      - FILENAME OF UTC WALLET (located in .data/.autonity/keystore) (example: UTC--2023-12-08T17-21-55.320411000Z--1af84c27d8f561e77dd15eddd4f665330b3e7844). Below will be dock acount import or generation.
      
   ### `SECURE_NETWORK_IP=""`
      - Parameter required if you do not use wireguard. You can set internal ip (for true isolated access or 0.0.0.0 - but i'ts NOT securt). Example. You server have private network, so, you can use this IP. 

  `Use wireguard guys and keep parameter unchanged.`
   

4. Run Toolkit.
   ## Toolkit WITH secure tunnel (Wireguard)
   ```
   ./tools/start_autonity_with_wireguard
   ```

      ## Toolkit WITHOUT! tunnel. (use only if you understand what you are doing)!!
   ```
   ./tools/start_autonity
   ```
