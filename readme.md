# Radicle-bins-docker 👏

More details [Radicle](https://radicle.xyz/).

## Build

`git clone https://github.com/garik-code/radicle-bins-docker`

`docker-compose up --build -d`

---

## Launch

`docker exec -it radicle bash`

Generate secret.key:

```
mkdir -p ~/.radicle-seed
cd /opt/radicle-bins/seed/ui
cargo run -p radicle-keyutil -- --filename ~/.radicle-seed/secret.key
```

Run radicle-seed-node:

```
cd /opt/radicle-bins/seed/ui
cargo run -p radicle-seed-node --release -- \
  --root ~/.radicle-seed \
  --peer-listen 0.0.0.0:12345 \
  --http-listen 0.0.0.0:80 \
  --name "YOUR NICKNAME" \
  --public-addr "YOUR IP ADDRESS:12345" \
  --assets-path /opt/radicle-bins/seed/ui/public \
  < ~/.radicle-seed/secret.key
```

---

[Radicle](https://radicle.xyz/) • [Radicle github](https://github.com/radicle-dev/radicle-bins) • [Running a seed node](https://docs.radicle.xyz/docs/using-radicle/running-a-seed-node)
