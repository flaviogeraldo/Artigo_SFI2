# paper-FGKCJ-2023-OMNeT

Optimal Resource Allocation with Delay Guarantees for Network Slicing in Disaggregated RAN

OMNeT++

We conduct all experiments in a Virtual Machine (VM) with 32 vCPUs, 256 GB RAM, and 100 GB of disk. VM is hosted in a server HPE ProLiant DL580 G7 with four Intel Xeon E7-4830 @ 2.13GHz. We used Python 3.8.10 and docplex 2.25.236 for implementing the optimization model and IBM CPLEX 22.1.1 as the optimal solver. We used Java Open-JDK 18.0.1 and DiscoDNC 2.4.4 to automate the estimation of bounds on end-to-end delay for the network topologies considered in this work using the following analyses: Total Flow Analysis (TFA), SFA, and Pay Multiplexing Only Once (PMOO). We carried out estimations for TFA and SFA using FIFO and Arbitrary multiplexing (ARB). The latter is also known in the literature as blind multiplexing. We implemented the network scenario depicted in Fig. 2 in OMNeT++ 6.0, using the INET framework 4.4 to compare the theoretical results with those obtained from simulations. Moreover, we assumed a traffic model based on a Poisson process to capture the dynamic behavior of the traffic downloaded from CU to each UE. Based on this simple assumption, we obtain a more realistic scenario where arrivals are modeled as a statistical distribution encompassing a non-full buffer model. In such a model, each UE has a specific throughput demand, i.e., the transmission rate ρ at which the UE downloads data. In our scenario, each active UE consumes a service related to a specific NSI (URLLC or eMBB). Each RU is associated with a specific vDU from the cell perspective, with different queues for different NSIs. Following a FIFO discipline, each queue receives traffic downloaded from CU (through the multiple transport nodes of the TN) to all the UEs related to a particular NSI and vDU. The buffer size is estimated not to present packet overflow, which is obtained using qmax from (6). The total number of queues in the network depends on the number of NSIs and vDUs. Regarding transmission capacity, the vDU resources are shared between these queues accordingly to a Weighted Round Robin (WRR) scheduling algorithm, which is used as the real-world scheduling algorithm that approximates the ideal scheduling algorithm (GPS). The WRR weights are related to the transmission capacity share in each transport node in (15). We estimate the number of Resource Blocks (RBs) demanded by each UE since the throughput demand of each UE is known by assuming a fixed MCS value and considering TTI as the baseline time unit for resource allocation. Additionally, the traffic is packetized with fixed packet sizes, and a small burst (equal to a packet size) is considered for each UE.
