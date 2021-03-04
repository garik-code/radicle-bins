# Radicle-bins-docker

## Build

`git clone radicle-bins`

`docker-compose up --build -d`

---

## Launch

`docker exec -it radicle bash`

Generate radicle-seed secret.key:

```
mkdir -p ~/.radicle-seed
cd /opt/radicle-bins/seed/ui
cargo run -p radicle-keyutil -- --filename ~/.radicle-seed/secret.key
```

Edit ip address and launch radicle-seed (peer-listen, http-listen):

```
cargo run -p radicle-seed-node --release -- \
  --root ~/.radicle-seed \
  --peer-listen 0.0.0.0:12345 \
  --http-listen 0.0.0.0:80 \
  --name "seedling" \
  --public-addr "seed.my.org:12345" \
  --assets-path seed/ui/public \
  < ~/.radicle-seed/secret.key
```

---

## Radicle

Repository [github](https://github.com/radicle-dev/radicle-bins)

Install [documentation](https://docs.radicle.xyz/docs/using-radicle/running-a-seed-node)
