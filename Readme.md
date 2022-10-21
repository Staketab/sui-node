# SUI NODE SETUP
Setup Sui Devnet node.

## 1. Install Docker-compose:
```
wget -q -O - https://bit.ly/3OcdIfO | bash -s -- 1.29.2
```
## 2. Clone repository:

```
git clone https://github.com/Staketab/sui-node.git
cd sui-node
```

## 3. Download Genesis:
```
wget -O $HOME/sui-node/genesis.blob https://github.com/MystenLabs/sui-genesis/raw/main/devnet/genesis.blob
```
## 4. Start the Node
Run this command to start the node:  
```
docker-compose up -d
```
-------------------------------
# REDEPLOY SUI NODE
After releasing new releases in Sui, you need to redeploy the node with the commands below:
```
cd sui-node
docker-compose pull
docker-compose down --volumes
rm -r $HOME/sui-node/suidb $HOME/sui-node/genesis.blob
wget -O $HOME/sui-node/genesis.blob https://github.com/MystenLabs/sui-genesis/raw/main/devnet/genesis.blob
docker-compose up -d
docker-compose logs -f sui
```

Other commands:
1. Stop docker-compose
```
docker-compose down
```
2. Docker-compose logs
```
docker-compose logs -f sui
```

# DONE