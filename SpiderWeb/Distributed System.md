Book: 
"Distributed Systems: Principles and Paradigms" by Andrew S. Tanenbaum and Maarten Van Steen
# I. Replication
![[Pasted image 20240630211745.png]]
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
Partitioning, also known as sharding, is a critical concept in designing scalable data-intensive applications. This section of the book delves into the principles and practices of partitioning data to improve scalability and performance.

#### Key Concepts in Partitioning:

1. **Why Partition?**
    
    - **Scalability**: By splitting data into partitions, you can distribute the load across multiple servers, allowing the system to handle more requests and store more data.
    - **Performance**: Partitioning can reduce the amount of data that needs to be scanned for a query, improving response times.
    - **Availability**: Distributing data across multiple nodes can improve fault tolerance. If one node fails, others can still function.
2. **Partitioning Strategies**
    
    - **Horizontal Partitioning (Sharding)**: Distributing rows of a table across multiple database instances. Each shard holds a subset of the rows.
    - **Vertical Partitioning**: Splitting a table into columns and distributing those columns across different databases. This is less common than horizontal partitioning.
3. **Choosing a Partitioning Key**
    
    - **Primary Key-Based Sharding**: Using the primary key to determine the partition. This method ensures uniform distribution if keys are random.
    - **Range-Based Partitioning**: Dividing data into ranges based on a key. This can lead to hot spots if data is not uniformly distributed.
    - **Hash-Based Partitioning**: Applying a hash function to the key to determine the partition. This ensures even distribution and avoids hot spots.
    - **Composite Key Partitioning**: Using a combination of multiple fields to determine the partition. This can balance the load better in complex scenarios.
4. **Rebalancing Partitions**
    
    - **Why Rebalance?**: Over time, partitions can become unbalanced due to changes in data distribution. Rebalancing ensures even load distribution.
    - **Splitting and Merging Partitions**: Techniques to split large partitions or merge small ones to maintain balance.
    - **Consistent Hashing**: A method to minimize data movement when adding or removing nodes in a cluster. It ensures that only a small portion of the data needs to be moved.
5. **Handling Partitioning in Practice**
    
    - **Routing Requests**: Mechanisms to route requests to the correct partition. This can be done using a directory service or client-side hashing.
    - **Distributed Joins and Transactions**: Handling joins and transactions across partitions is complex. Techniques include two-phase commit for distributed transactions and map-reduce for joins.
    - **Secondary Indexes**: Maintaining secondary indexes across partitions can be challenging. Indexes can either be partitioned in the same way as the primary data or maintained separately.
6. **Fault Tolerance and Replication**
    
    - **Replication Strategies**: Combining partitioning with replication to ensure high availability and fault tolerance. Each partition can be replicated to multiple nodes.
    - **Consistency Models**: Ensuring consistency across partitions and replicas. Techniques include quorum-based replication and conflict resolution mechanisms.
7. **Examples and Case Studies**
    
    - **Real-World Systems**: The book provides examples from real-world systems like Google Bigtable, Amazon DynamoDB, and Apache Cassandra. These examples illustrate different partitioning strategies and their trade-offs.


![[Pasted image 20240617214851.png]]
# III. Transactions
#### 1. **ACID Properties**

- **Atomicity**: Ensures that a series of operations within a transaction are treated as a single unit, which either completely succeeds or completely fails.
- **Consistency**: Ensures that a transaction brings the database from one valid state to another, maintaining database invariants.
- **Isolation**: Ensures that concurrently executed transactions do not interfere with each other, maintaining the illusion that transactions are executed sequentially.
- **Durability**: Guarantees that once a transaction is committed, its changes are permanent, even in the event of a system crash.
#### 2. **Concurrency Control**

- **Locking**: Uses locks to control access to data. It includes techniques like two-phase locking (2PL) to ensure serializability but can lead to issues like deadlocks.
- **Optimistic Concurrency Control**: Assumes conflicts are rare and checks for conflicts only at the end of a transaction. If a conflict is detected, the transaction is aborted and retried.
- **Snapshot Isolation**: Each transaction works with a consistent snapshot of the database, avoiding conflicts by ensuring transactions do not overwrite each other's changes.

#### 3. **Isolation Levels**

- **Read Uncommitted**: Allows transactions to see uncommitted changes from other transactions, leading to potential dirty reads.
- **Read Committed**: Prevents dirty reads by ensuring transactions only see committed changes, but can still allow non-repeatable reads.
- **Repeatable Read**: Ensures that if a transaction reads a value, it will see the same value if it reads again, preventing non-repeatable reads but not phantom reads.
- **Serializable**: The highest isolation level, ensuring complete isolation from other transactions, effectively achieving serializability but at a higher performance cost.

#### 4. **Distributed Transactions**

- **Two-Phase Commit (2PC)**: A protocol used to ensure all participants in a distributed transaction either commit or abort the transaction, involving a prepare and a commit phase. However, it can be slow and is prone to becoming a bottleneck.
- **Three-Phase Commit (3PC)**: An extension of 2PC designed to reduce the risk of blocking participants in the event of a coordinator failure.

#### 5. **Handling Failures**

- **Crash Recovery**: Techniques for ensuring durability and atomicity, such as write-ahead logging (WAL) and checkpoints.
- **Undo and Redo Logging**: Methods for recovering from crashes by either undoing partial transactions (undo logging) or reapplying committed transactions (redo logging).

#### 6. **Weak Isolation Levels**

- **Eventual Consistency**: In distributed systems, achieving strong consistency is often impractical, so systems may use weaker consistency models like eventual consistency, where updates propagate asynchronously, and all replicas eventually converge.

#### 7. **Practical Considerations**

- **Choosing Isolation Levels**: Trade-offs between performance and isolation level, depending on the application requirements.
- **Design Patterns for Transactions**: Best practices for designing systems that use transactions, such as minimizing the duration of transactions and avoiding long-running transactions.