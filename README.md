# Hello world on eosio

An eos.io smart contract that says hi to whichever username specified.

## Image example

Sample image of it running

<img src="./Assets/Screenshot from 2018-07-16 00-10-19.png">

## Getting Started
eosiocpp -n HelloWorld
 2142  eosiocpp -g HelloWorld.abi HelloWorld.cpp
 2144  eosiocpp -o HelloWorld.wast HelloWorld.cpp


Clone the repository. To run it nodeos and keosd, you just run 
```
sudo docker-compose up -d
```

Create a wallet
```
./cleos.sh wallet create
```

Import this key to the wallet (yes this key represents the eosio producer default key)
```
./cleos.sh wallet import 5KQwrPbwdL6PhXujxW37FSSQZ1JiwsST4cqQzDeyXtP79zkvFD3
```

Generate the abi file
```
./eosiocpp -g HelloWorld.abi HelloWorld.cpp
```

Generate the wast file
```
./eosiocpp -o HelloWorld.wast HelloWorld.cpp
```

Set the contract to the blockchain
```
./cleos.sh set contract eosio ~/Documents/eos/build/contracts/eosio.bios -p eosio@active
```

Use eosio to create a new account (in this case hello)
```
./cleos.sh create account eosio hello EOS6MRyAjQq8ud7hVNYcfnVPJqcVpscN5So8BhtHuGYqET5GDW5CV EOS6MRyAjQq8ud7hVNYcfnVPJqcVpscN5So8BhtHuGYqET5GDW5CV
```

Push the actions to the blockchain!
```
./cleos.sh push action hello hi '["user"]' -p hello@active
./cleos.sh push action hello hi '["dolores"]' -p hello@active
./cleos.sh push action hello hi '["akecheta"]' -p hello@active
```

### Prerequisites

Install docker
```
sudo apt-get install docker-ce
```

Install docker-compose
```
sudo apt-get install docker-compose
``` 

### Installing

To install all the node modules, just type

```
sudo docker-compose up -d
```


