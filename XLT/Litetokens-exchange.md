# LITETOKENS Mainnet - Integration Guide

Connecting to the LITETOKENS network is extremely easy and only requires running 1-2 nodes on a machine. Once you've connected to the network, you have multiple ways of interacting with the nodes based on your system's requirements. When you're fully integrated, please reach out to the LITETOKENS team so that we can help you verify your setup.

- [Full LITETOKENS Documentation](https://github.com/litetokens/Documentation/blob/master/XLT/Litetokens-overview.md)

# 1. Deploy LITETOKENS Nodes

You'll need to deploy nodes that connect to the network and offer both the ability to read the blockchain state and also to broadcast transactions onto the network.

LITETOKENS's network uses a Full Node to read and broadcast to the network. The Full Node stores the entire blockchain state, including unconfirmed blocks and potential forks. 

Deploying a linked Solidity Node allows you to interact with blocks that are guaranteed confirmed and irreversible.

Follow this guide to deploy a Full Node and a linked Solidity Node on the same machine.
- [Node Deployment Guide](https://github.com/litetokens/Documentation/blob/master/XLT/Solidity_and_Full_Node_Deployment_EN.md)

# 2. Integrate with the LITETOKENS nodes

The nodes support both a gRPC Service and a HTTP Gateway on the ports specified in the configuration files. You can use either method to communicate with the nodes. 
- [Full API documentation](https://github.com/litetokens/Documentation/blob/master/XLT/Litetokens-overview.md#4-litetokens-api)

### gRPC 

[gRPC](https://grpc.io/) uses Protobuf and the [LITETOKENS protocol](https://github.com/litetokens/protocol).

### HTTP Gateway

The nodes also offer an alternate RESTful HTTP Gateway.
Read the [HTTP Documentation](https://github.com/litetokens/Documentation/blob/master/XLT/Litetokens-http.md) for examples.

## Build your custom integration. 

Take a look at the [Common Patterns](https://github.com/litetokens/Documentation/blob/master/XLT/Common-Patterns.md) guide for some basic assistance.

# 3. Testing

Once you've fully integrated with the network, please test on both the test network and the main network.

### Mainnet
- Block Explorer: https://LITETOKENSscan.org
- Config: https://github.com/LITETOKENSprotocol/LITETOKENSDeployment/blob/master/main_net_config.conf

### Testnet
- Block Explorer: https://test.LITETOKENSscan.org
- Config: https://github.com/LITETOKENSprotocol/LITETOKENSDeployment/blob/master/test_net_config.conf

