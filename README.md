# BUILDING

*For internal testing using Umba, compile via Dockerfile.*

## Two Commands
- `beam-wallet` 
- `beam-node`

## Setting Up Wallet
You can either set up the wallet or node first. I usually start with the wallet.
Configurations can also be specified in `beam-wallet.cfg`.

- Initializing Wallet
  - `./beam-wallet --command init`
  - You will be prompted to input a wallet password. 
  - Wallet phrase will be generated for you.
  - New address will be generated and output.
- Export Owner Viewer Key (one confidential key to view only) key_owner
  - `beam-wallet --command=key_export`
  - You will be prompted to input the wallet password that you defined during initialization.
  - Owner Viewer key will be output.
- Export secret miner key for miner N (subkey) key_mine
  - `beam-wallet --command=key_export --subkey=1`
  - You will be prompted for the wallet password.
  - Secret Subkey will be output.

_At this point, I set up beam node_
- Start Mining Node
  - `beam-node --port 8100 --peer 10.1.0.6:8100 10.1.0.10:8100 10.1.0.14:8100 10.1.0.18:8100 10.1.0.22:8100 10.1.0.26:8100 10.1.0.30:8100 10.1.0.34:8100 10.1.0.38:8100 --mining_threads 1`
  - List your peers and their respective ports.
  - `--mining_threads 1` starts mining.
  - It will attempt to connect to all of the peers, even if they aren't set up and configured yet.

_And back to wallet_ 
- Sync with node and listen
  - `beam-wallet --command listen -n <node address and port, ex: 127.0.0.1:10000`

_Additional Commands_
- Get Wallet Info
  - `beam-wallet --command=info`
- SBBS
  - Generate new address
    - `beam-wallet --command=new_addr -n 127.0.0.1:10000 //--listen`
  - Sending beams
    - `beam-wallet --command=send -n 127.0.0.1:10000 -r 77de6bd3de40bc58ab7e4fb68d5e0596fd1e72f3c4fb3eb3d106082d89264909 -a 11.3 -f 0.2`

## NOTES

### P2P 

- Uses libuv p2p and Dandelion protocol for anonymity
- Traditional Gossip protocol after Dandelion
- Uses bootnode system
- Each peer has rating 
- Reputation based, uses scoring system
- Each peer will retry, *should* give it another chance before banning. It seems as if this functionality isn't working right. Currently, node will continue to attempt to peer with unreachable host forever.
- Weighted round robin with some preference involved

### Mining 
- Equihash 150,5


