# Xeggo-SDK Documentation

# 1. Introduction

## 1.1 About Xeggo Streaming Service

Xeggo is a Token/ Money streaming platform, built on the Celo blockchain. The user can create, start or schedule money streams which will enable funds to be transferred to the target reciever over a period of time with a defined rate of transfer. <br> This manual provides technical details and instructions of the Xeggo SDK and how to make use of it in your projects.


# 2. Initial Setup
The following procedure describes how you initialise the setup to use Xeggo functionalities in your project.
## To initialise Xeggo SDK without private key
```javascript
import{framework} from './framework.js'
//Use setContractInstance() and setTokenInstance() if you don't want to use default contract and token.
const xeggo = new framework
xeggo.initialiseWithKey(44787)//Enter ChainId here, *Only for call functions not for sending transactions to the smart contract*
await xeggo.getBalance(streamId,recepient)
await xeggo.getStream(streamId)
```
## To initialise Xeggo SDK with private key( To send transactions to functions )
```javascript
import { framework } from './framework.js'
const xeggo = new framework
xeggo.initialiseWithKey('enterPrivateKeyHere', 44787)
await xeggo.createStream('recepient', deposit, 'tokenAddress', streamTime)
```
# 3. Available functions 
```xeggo.getBalance()```: Returns the balance of the stream in number of tokens
```xeggo.getStream()```:Returns details of a stream
```xeggo.cancelStream()```:Cancels ongoing/ started streams
```xeggo.createStream()```:Creates/ Starts a new stream
```xeggo.withdrawFromStream()```:Withdraws funds from completed stream (For recipient)
