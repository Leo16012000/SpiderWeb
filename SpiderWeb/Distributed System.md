Book: 
"Distributed Systems: Principles and Paradigms" by Andrew S. Tanenbaum and Maarten Van Steen
# I. Replication
## 1. Single Leader/primary-replica/master-slave
One leader handle all writes
Propagate changes to followers
Able to read from any replica
Pros: Consistency cause single source of truth
Cons: Leader bottleneck
## 2. Multi-leader
reach any leaders
* communicates the write to other followers, including other leaders
## 3. Leaderless
# II. Partitioning


![[Pasted image 20240617214851.png]]
# III. Transactions
