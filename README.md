# Neo4jDB HA Implementation
This project is trying to implement HA on Neo4j community.</br> 
You can start a 3-node neo4j cluster, and use our client and coordinators to send RPC requests to the cluster.
- - -
# 1. Requirement
1. Java Version 1.8
2. Scala Version **MUST BE** 2.11.0
- - -
# 2. How to run(Suppose you only run a 3-node cluster) 
1. Start your Neo4j server(3 nodes).
2. Start your Zookeeper cluster(3 nodes).
3. run the "DistributeServer.java" in every node.
4. run the "Coordinator.scala" in every node.

Then you can run "RpcClient.scala" choose 'WriteCypher' or 'ReadCypher' (in line 36) to send your Cypher statement to cluster, and see the result from RpcClient console.
