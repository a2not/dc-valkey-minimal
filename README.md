# example docker compose for valkey cluster connection

Turns out dynamically specifying `--cluster-announce-hostname` was the key to connect valkey cluster with hostname like `valkey-cluster:6379`.

Besides, we need to fix IP address in order to avoid saving cluster config (such as `7001.conf`) later misaligned with the actual container IP address.

Even if we set `--cluster-announce-hostname`, valkey writes IP address in the cluster config file.

```sh
docker compose up --build

docker compose down --volumes --remove-orphans
```
