# Beam Test Plan:  

## Test Procedure

Per test case:
1. Build network
2. Provision nodes
3. Configure network conditions between nodes according to specified test case
4. Configure actions and behavior between nodes according to specified test case
5. Output performance data in CSV format
6. Aggregate data, parse, & present data
8. Push data to appropriate repo, if necessary
9. Reset environment

## Test Utilities  

Tests will be conducted using the [Whiteblock](https://www.whiteblock.io) testing platform, a cloud-based SaaS solution. The Whiteblock framework will build and manage the P2P network topology and automate particulate actions in accordance with the proposed scope of work outlined within this document. 

## Node Specifications

| Component   | Value                                          |
|-------------|------------------------------------------------|
| RAM         | 4GB DDR4                                       |
| CPU         | Intel Xeon Scalable Processor (Skylake)        |
| Single-Core Max Turbo Frequency  | 3.5 Ghz                   |
| Total Node Count  | 32                                       |


## Performance Metrics

Time measurements are expressed in terms of the time passed on the node
coordinating the tests.  Assuming the coordinating node's clock hasn't been tempered with.

| Value			            | Description | 
| ------------------------- | -------- | 
| Bootstrap Time	        | The length of time it takes for a node to become aware of its peers within the network. | 
| Block Propagation Time    | The length of time it takes for a block to be received by all nodes within the network. |
| Orphan Rate    	        | The frequency at which orphan blocks are mined and broadcast.                           | 
| Transactions Per Second   | The total amount of transactions which can be successfully processed per second. Transaction time begins when a transaction is submitted and ends when the UTXO is transferred to the receiving account. |


## Performance Tests

The following tables define each test series within this test phase. A test
series focuses on observing and documenting the effects of certain conditions
on performance. Each test series is comprised of three separate test cases
which define the variable to be tested. 

(_Note_: The numbers listed below are subjected to change)

### Series 1: Number of Miners

| Variable         | Test Case A | Test Case B | Test Case C |
|------------------|------------:|------------:|------------:|
| Miners           | 10          | 20          | 30          |
| Transaction Node | 22          | 12          | 2           |
| Sent Tx Per Node |  100        |  100        | 100         |
| Bandwidth        | 1Gb         | 1Gb         | 1GMb        |
| Network Latency  | 0ms         | 0ms         | 0ms         |
| Packet Loss      | 0%          | 0%          | 0%          |


### Series 2: Number of Transactions per Node

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 600         | 600         | 600         |
| Non-Miner Nodes    | 600         | 600         | 600        |
| __Number of Txs Per Node Per Second__ |  100  |  200  |   300     |
| Size of Txs |  10Mb  |  10Mb  |   10Mb    |
| Bandwidth       | 5Mb         | 5Mb         | 5Mb         |
| Network Latency | 0ms         | 0ms         | 0ms         |
| Packet Loss     | 0%          | 0%          | 0%          |


### Series 3: Size of Transactions

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 600         | 600         | 600         |
| Non-Miner Nodes    | 600         | 600         | 600        |
| Number of Txs Per Node Per Second|  100  |  200  |   300     |
| __Size of Txs__ |  10Mb  |  20Mb  |   30Mb    |
| Bandwidth       | 5Mb         | 5Mb         | 5Mb         |
| Network Latency | 0ms         | 0ms         | 0ms         |
| Packet Loss     | 0%          | 0%          | 0%          |



### Series 4: Bandwidth

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 1000        | 1000        | 1000        |
| Non-Miner Nodes    | 1000        | 1000        | 1000        |
| Non-Miner Nodes    | 1000        | 1000        | 1000        |
| Number of Txs Per Node Per Second|  100  |  100  |   100     |
| __Bandwidth__       | 5Mb         | 500Mb       | 1G          |
| Network Latency | 0ms         | 0ms         | 0ms         |
| Packet Loss     | 0%          | 0%          | 0%          |


### Series 5: Network Latency

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 1000        | 1000        | 1000        |
| Non-Miner Nodes    | 1000        | 1000        | 1000        |
| Number of Txs Per Node Per Second|  100  |  100  |   100     |
| Non-Miner Nodes    | 1000        | 1000        | 1000        |
| Bandwidth       | 5Mb         | 5Mb         | 5Mb         |
| __Network Latency__ | 25ms        | 50ms        | 100ms       |
| Packet Loss     | 0%          | 0%          | 0%          |


### Series 6: Packet Loss

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 1000        | 1000        | 1000        |
| Non-Miner Nodes    | 1000        | 1000        | 1000        |
| Number of Txs Per Node Per Second|  100  |  100  |   100     |
| Size of Txs |  10Mb  |  10Mb  |   10Mb    |
| Bandwidth       | 5Mb         | 5Mb         | 5Mb         |
| Network Latency | 0ms         | 0ms         | 0ms         |
| __Packet Loss__     | 0.01%       | 0.5%        | 1.0%        |

