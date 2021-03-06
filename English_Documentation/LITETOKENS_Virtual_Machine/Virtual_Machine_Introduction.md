# LITETOKENS Virtual Machine (LVM)

LITETOKENS Virtual Machine (LVM) is a lightweight, Turing complete virtual machine developed for the LITETOKENS's ecosystem. Its goal is to provide millions of global developers with a custom-built blockchain system that is efficient, convenient, stable, secure and scalable.

LVM can connect seamlessly with existing development ecosystem and supports DPOS. LVM is able to be compatible with EVM environment in the beginning, so that instead of learning a new programming language, developers can develop, debug and compile smart contracts in a Remix environment with Solidity and other languages. Once you’ve built and uploaded your smart contract to LITETOKENS’s mainnet, it will be executed on the LVM of the LE node to be isolated from external connections.

Furthermore, LVM employs the concept of Bandwidth. Different from the gas mechanism on Ethereum’s  EVM,  operations of transaction or smart contracts on LVM are free, with no tokens consumed. Technically, executable computation capacity on LVM is not restricted by total holding of tokens.

## Features of LVM
1. Lightweight
LVM adopts a lightweight architecture with the aim of reducing resource consumption to guarantee system performance.
2. Stability and security
With a meticulous design paradigm and fine-grained underlying operation code, LVM can guarantee the preciseness of every step of a computation, diminishing ambiguity to the largest extent. Out of security reasons, transfers and smart contract running cost only bandwidth points, not XLT, which exempts LITETOKENS from being attacked similarly to Ethereum for its mode of gas consumption. Stability of bandwidth consumption is achieved while the cost of each computational step is fixed.
3. Compatibility
Currently, LVM is compatible with EVM and will be with more mainstream VMs in the future. Thereby, all smart contracts on EVM are executable on LVM. By connecting seamlessly to existing development ecosystem, higher efficiency can be achieved by developers. Needless to learn a new programming language, they can use mainstream programming languages for smart contract such as Solidity to develop, debug and compile smart contracts in the Remix environment, which greatly reduces development costs.
4. Developer-friendly
Thanks to LVM’s bandwidth setup, developments costs are reduced and developers can focus on the logic of their contract code. LVM also offers all-in-one interfaces for contract deployment, triggering and viewing, for the convenience of developers.  
The following interfaces are available in Litetokens Wallet-CLI:
+ deploycontract(password, contractAddress, ABI, code, data, value)
+ triggercontract(password, contractAddress, selector, data, value)
+ getcontract(contractAddress)
Developers can call these interfaces to deploy, trigger or check smart contracts.

## How LVM works
	
![Flowchart of Litetokens Virtual Machine](https://raw.githubusercontent.com/ybhgenius/Documentation/master/images/Virtual_Machine/虚拟机.png)

The above flowchart shows how LVM works:  
Compilation of Litetokens smart contract→execution and computing engines of VM→Interoperation service layer for external interfaces

Put simply, the flow is as follows:
+ Currently, LVM is compatible mainly with Solidity. The compiler translates Solidity smart contract into bytecode readable and executable on LVM.
+ A virtual machine processes data through opcode, which is equivalent to operating a logic of a stack-based finite state machine.
+ LVM accesses blockchain data and invoke External Data Interface through the Interoperation layer.

## Future development of LVM
1. More developer-friendly debugging tools  
Litetokens will be committed to the development of optimized debugging tools and the establishment of standardized symbol and data format, for improved developer efficiency.
2. Fulfillment of diversified processing demands  
Different from gas consumption mechanism for every transaction on EVM, there is no charge on LVM. Each operation only occupies bandwidth, which will be released within a certain amount of time after completion of transaction. It takes developers very little to develop smart contracts with more complex logic. It is our belief that besides being used for digital asset transactions, smart contracts could also be suitably applied to areas such as game development, financial risk modeling and scientific computing. The design of LVM inherently supports multi-scenario tasks, and further optimizations of processing speed, response time, and floating point compatibility. 
3. Improvement of Just-In-Time (JIT) compilation speed and integration of WebAssembly

Improving JIT compilation speed is conducive to faster interpretation and optimized compilation of local code.  
Meanwhile, Litetokens is planning to further optimize its LVM based on WebAssembly (WASM). WebAssembly, spearheaded by Apple, Google, Microsoft and Mozilla, is designed to break bottlenecks of current Web browsers and can be generated through compiling C/C++ and other programming languages.  
Integrating WASM, LVM will be able to provide high performance and high throughput for blockchain to cope with complex scenarios.

## The following is a guide to LVM (smart contract deployment)

1. Compile contract
Contract compilation address: https://remix.ethereum.org
2. Get ABI and bytecode  
```
        pragma solidity^0.4.11;

        contract Litetokens {
            uint256 litetokens;
            constructor() public { }
    
    
            function set(uint256 number) public returns(bool){
                litetokens = number;
                return true;
            }
        }

        ABI: 
        [{“constant":false,"inputs":[{"name":"number","type":"uint256"}],"name":"set","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"inputs":[],"payable":false,"stateMutability":"nonpayable","type":"constructor"}]


        ByteCode：608060405234801561001057600080fd5b5060c48061001f6000396000f300608060405260043610603f576000357c0100000000000000000000000000000000000000000000000000000000900463ffffffff16806360fe47b1146044575b600080fd5b348015604f57600080fd5b50606c600480360381019080803590602001909291905050506086565b604051808215151515815260200191505060405180910390f35b600081600081905550600190509190505600a165627a7a723058209791df3f67e9af451c35d7ae55bda5e352764f6a38ea23fa850b1c1fe1bc72e90029
```
3. Deploy contract  
Wallet-cli-vm branch: https://github.com/litetokens/wallet-cli/tree/wallet-cli-vm    
Java-litetokens-vm branch: https://github.com/litetokens/java-litetokens/tree/develop_vm  
Password: password of client-end wallet  
ContractAddress: customized contract address (in Litetokens’s required format)  
ABI: interface description  
Data: parameters of the initial function  
Value: reserved field  
deploycontract(Password, ContractAddress, ABI, Code, Data, Value)  
4. Invoke contract  
Selector: function selector  
Data: parameters  
triggercontract(Password, ContractAddress, Selector, Data, Value)  
5. Check contract
```
    getcontract(ContractAddress)
```

The above is an introduction of Litetokens Virtual Machine and a guide to deployment. We welcome everyone to check out LVM and give us your thoughts and suggestions. We will continue to perfect and update LVM for optimal performance on LITETOKENS mainnet.
