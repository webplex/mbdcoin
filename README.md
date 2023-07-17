# mbdcoin
mbd blockchain

# mkdir /home/data/MBD/
# cd /home/data/MBD/
# wget https://www.mbdtop.com/API/mbd.tar.gz
# tar -zxf mbd.tar.gz
# ./mbd --datadir=/home/data/MBD/ init /home/data/MBD/genesis.json

--rpc --rpcaddr 127.0.0.1 --rpcport PORT --rpcapi eth,personal,web3
# nohup ./mbd --datadir=/home/data/MBD/ --rpc --rpcaddr 127.0.0.1 --rpcport **** --rpcapi eth,personal,web3 --rpccorsdomain "127.0.0.1" --port **** --nodiscover --networkid 55125 &

# ./mbd attach ipc:./geth.ipc
> admin.addPeer("enode://c9620ccf92ef5952489ccf8b9653161bb7e41c230b352b1f045da102ba096d104782aa67ea0b5e17e9696fb32d0b71aefb062b027061aa6136801ffad4987ee9@210.106.251.103:6667?discport=0")
> admin.peers
[
.........
]
> exit;
>

1. rpc communication of local node
# curl -X POST -H "Content-Type:application/json" --data '{"jsonrpc":"2.0","method":"personal_newAccount","params":["PASSWORD"],"id" :1}' 127.0.0.1:****
# result :
{"jsonrpc":"2.0","id":1,"result":"0x........"}
Create private key file in AND keystore directory

2. rpc communication of remote node
# curl -X POST -H "Content-Type:application/json" --data '{"jsonrpc":"2.0","method":"personal_newAccount","params":["PASSWORD"],"id" :1}' ip:port

3.Offline transaction construction and related codes
# curl -X POST -H "Content-Type: application/json" --data '{"jsonrpc":"2.0","method":"eth_sendTransaction","params":[{"from": "0x3d62f78896fa1db61f1447f1d19e0e49cc3b03ac", "to": "0x93473faa664f8534acf48a14d6041cfcc9ec70f5", "value": "0x6bc3376345ebfa5000"}],"id":1}' http://localhost:****

* SUCCESS Case (Verifies that the status value is true)
https://www.mbdtop.com/API/?hash=0x039ec1ff74688fcb3dfc2dcc3e03cd43c40c73585f998220e2c1b54c1d38422d
{
  "RES": "200",
  "MSG": [
    {
      "blocknum": "118224",
      "hash": "0x039ec1ff74688fcb3dfc2dcc3e03cd43c40c73585f998220e2c1b54c1d38422d",
      "amount": "5.000000000000000000",
      "from": "0x03b6f4ce918cfeed691243a92921018f1933ea64",
      "to": "0x2d3e245a2aa56ff70a7adeb6a69389030ad21a39",
      "status": true
    }
  ]
}
