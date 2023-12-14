## Games.

### Update repo and generate your api key with command

```
git pull
./tools/rebuild_docker_images aut_client
./tools/generate_api_signature
```

Then, you can use commands from Official docs (https://game.autonity.org/getting-started/exchange-cax.html)

Example request
```
https GET https://cax.piccadilly.autonity.org/api/orderbooks/ API-Key:$(./tools/get_aut_api_key)
```
