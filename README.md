# T3rn-V2-set-up
How to set up t3rn Executor node (V2)
Follow this instructions, step by step and you're good 👍


## 1️⃣ Remove Existing Node (If Any)  
Before installing or setting up a new instance of the t3rn node, remove any existing installation using the following command:  
```sh
rm -rf t3rn
```
## 2️⃣ Create a New Directory and Navigate Into It

Run the following commands to create a new directory for the t3rn node and move into it:
```sh
mkdir t3rn
cd t3rn
```
## 3️⃣ Download the Latest t3rn Release

Fetch and download the latest t3rn executor release using the following command:
```sh
curl -s https://api.github.com/repos/t3rn/executor-release/releases/latest | \
grep -Po '"tag_name": "\K.*?(?=")' | \
xargs -I {} wget https://github.com/t3rn/executor-release/releases/download/{}/executor-linux-{}.tar.gz
```
## OR Specify the version by edititng this

Replace the version you want to install
```sh
VERSION="v0."
wget "https://github.com/t3rn/executor-release/releases/download/${VERSION}/executor-linux-${VERSION}.tar.gz"
```
## 4️⃣ Extract the Downloaded Archive

Once the download is complete, extract the files using:
```sh
tar -xzf executor-linux-*.tar.gz
```

## 5️⃣ Navigate to the Binary Directory

Move into the directory containing the extracted executable files:
```sh
cd executor/executor/bin
```

## 6️⃣ Install Screen (If Not Installed)

If screen is not already installed on your system, install it using:
```sh
sudo apt update && sudo apt install screen -y
```
## 7️⃣ Start a Screen Session

To keep the process running in the background, start a new screen session named t3rn:
```sh
screen -S t3rn
```

## 8️⃣ Set the Environment Variables
```sh
export ENVIRONMENT=testnet
```

```sh
export LOG_LEVEL=debug
export LOG_PRETTY=false
```

```sh
export EXECUTOR_PROCESS_BIDS_ENABLED=true
export EXECUTOR_PROCESS_ORDERS_ENABLED=true
export EXECUTOR_PROCESS_CLAIMS_ENABLED=true
```

```sh
export EXECUTOR_MAX_L3_GAS_PRICE=1000
```

```sh
export ENABLED_NETWORKS='arbitrum-sepolia,base-sepolia,optimism-sepolia,blast-sepolia,unichain-sepolia,l2rn'
```

```sh
export PRIVATE_KEY_LOCAL=your_private_key
```

```sh
export EXECUTOR_PROCESS_BIDS_ENABLED=true
export EXECUTOR_ENABLE_BATCH_BIDING=true
```

```sh
export EXECUTOR_PROCESS_PENDING_ORDERS_FROM_API=false
export EXECUTOR_PROCESS_ORDERS_API_ENABLED=false
```

```sh
export RPC_ENDPOINTS='{
    "l2rn": ["https://t3rn-b2n.blockpi.network/v1/rpc/public", "https://b2n.rpc.caldera.xyz/http"],
    "arbt": ["https://arbitrum-sepolia.drpc.org", "https://sepolia-rollup.arbitrum.io/rpc"],
    "bast": ["https://base-sepolia-rpc.publicnode.com", "https://base-sepolia.drpc.org"],
    "blst": ["https://sepolia.blast.io", "https://blast-sepolia.drpc.org"],
    "opst": ["https://sepolia.optimism.io", "https://optimism-sepolia.drpc.org"],
    "unit": ["https://unichain-sepolia.drpc.org", "https://sepolia.unichain.org"]
}'
```
## 9️⃣ Start the Execution node
```sh
./executor
```
### Once you see this, you're now successfully running T3rn V2 executor node.
![Successful Executor](https://github.com/Tony-smile/T3rn-V2-set-up/blob/main/20250318_183311.jpg)

### Exit screen mode
Ctr + A then D

### Reattache screen incase of next time you want to assess your node
Screen -r t3rn

## 🔟 Additional things to do
You need Sepolia faucet across 
Base, Arbitrum, Optimism, l2rn, blast and unichain in order to continue executing well.

## 🔥Most importantly you need gas fee on B2n to even START EXECUTING.

## Claim BRN Faucet  

Claim your BRN faucet here:  
🔗 [b2n.hub.caldera.xyz](https://b2n.hub.caldera.xyz)  

## Check Your BRN Earnings  

Connect your wallet here and see how much $BRN you have earned:  
🔗 [bridge.t2rn.io](https://bridge.t2rn.io/)


