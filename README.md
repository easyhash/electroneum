# Daemon
```bash
docker run --name ElectroneumDaemon --volume daemon:/daemon/data easyhash/electroneum:latest /daemon/electroneumd --log-level=0 --rpc-bind-ip=0.0.0.0 --rpc-bind-port=18081 --data-dir=/daemon/data --confirm-external-bind
```

# Wallet
```bash
docker run --name ElectroneumWallet --volume wallet:/daemon/data --link ElectroneumDaemon:daemon easyhash/electroneum:latest /daemon/electroneum-wallet-rpc --daemon-address=http://daemon:18081 --wallet-file=/daemon/data/electroneum.wallet --rpc-bind-ip=0.0.0.0 --rpc-bind-port=18082 --confirm-external-bind --trusted-daemon --disable-rpc-login --password '<wallet password>' --log-level=0
```