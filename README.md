# hemi-miner

here full official tutorial

wget https://github.com/hemilabs/heminetwork/releases/download/v0.3.13/heminetwork_v0.3.13_linux_amd64.tar.gz

mkdir hemi

tar -xzvf heminetwork_v0.3.13_linux_amd64.tar.gz -C hemi/

cd hemi

./popmd --help

./keygen -secp256k1 -json -net="testnet" > ~/popm-address.json

nano popm-address.json

Edit according to yours (you will not need to do anything directly with your public key.)
save ctrl + x and y enter

export POPM_BTC_PRIVKEY=yourpk
export POPM_STATIC_FEE=400
export POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public


run

./popmd 
