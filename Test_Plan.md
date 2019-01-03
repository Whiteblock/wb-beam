# WB Beam Test Plan: 

## Test Procedure

Per test case:
1. Build network
2. Provision nodes
3. Configure network conditions between nodes according to specified test case
4. Configure actions and behavior between nodes according to specified test case
5. Output performance data in CSV format
6. Aggregate data, parse, & present data
8. Push data to appropriate repo
9. Reset environment


## Test Environment

The proposed testing initiatives will be conducted within the Whiteblock test
lab on a group of 6 rack mounted chassis servers.

Should testing initiatives require additional computational resources or
demand a higher overhead than can be adequately provided within the proposed
environment, the Whiteblock cloud-based solution can be used. However, in the
interest of cost-effectiveness, the current on-premises lab setup can
adequately provide the current scope of work. 


## Performance Tests

The following tables define each test series within this test phase. A test
series focuses on observing and documenting the effects of certain conditions
on performance. Each test series is comprised of three separate test cases
which define the variable to be tested. 

### Series 1: Number of Validators

| Variable         | Test Case A | Test Case B | Test Case C |
|------------------|------------:|------------:|------------:|
| Miners       | 300         | 600         | 1000        |
| Static Nodes     | 600         | 600         | 600         |
| Bandwidth        | 5Mb         | 5Mb         | 5Mb         |
| Propagation Time | 8s          | 8s          | 8s          |


### Series 2: Number of Static Nodes

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 600         | 600         | 600         |
| Static Nodes    | 300         | 600         | 1000        |
| Bandwidth       | 5Mb         | 5Mb         | 5Mb         |
| Network Latency | 0ms         | 0ms         | 0ms         |
| Packet Loss     | 0%          | 0%          | 0%          |


### Series 3: Contract

| Variable        | Test Case A | Test Case B   | Test Case C   |
|-----------------|------------:|--------------:|--------------:|
| Miners      | 1000        | 1000          | 1000          |
| Static Nodes    | 1000        | 1000          | 1000          |
| Bandwidth       | 5Mb         | 5Mb           | 5Mb           |
| Network Latency | 0ms         | 0ms           | 0ms           |
| Packet Loss     | 0.01%       | 0.5%          | 1.0%          |


### Series 4: Bandwidth

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 1000        | 1000        | 1000        |
| Static Nodes    | 1000        | 1000        | 1000        |
| Bandwidth       | 5Mb         | 500Mb       | 1G          |
| Network Latency | 0ms         | 0ms         | 0ms         |
| Packet Loss     | 0%          | 0%          | 0%          |


### Series 5: Network Latency

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 1000        | 1000        | 1000        |
| Static Nodes    | 1000        | 1000        | 1000        |
| Bandwidth       | 5Mb         | 5Mb         | 5Mb         |
| Network Latency | 25ms        | 50ms        | 100ms       |
| Packet Loss     | 0%          | 0%          | 0%          |


### Series 6: Packet Loss

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 1000        | 1000        | 1000        |
| Static Nodes    | 1000        | 1000        | 1000        |
| Bandwidth       | 5Mb         | 5Mb         | 5Mb         |
| Network Latency | 0ms         | 0ms         | 0ms         |
| Packet Loss     | 0.01%       | 0.5%        | 1.0%        |


### Series 7: Stress Test

| Variable        | Test Case A | Test Case B | Test Case C |
|-----------------|------------:|------------:|------------:|
| Miners      | 1000        | 500         | 300         |
| Static Nodes    | 2000        | 2000        | 2000        |
| Bandwidth       | 5Mb         | 5Mb         | 5Mb         |
| Network Latency | 50ms        | 50ms        | 50ms        |
| Packet Loss     | 0.01%       | 0.01%       | 0.01%       |

