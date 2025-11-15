# Building-Modern-Distributed-Systems

Environment Setup 
  1. cd Environment Setup
  2. cd docker
  3. vi docker-compose [to view the docker compose file. You can see the definition of several services that will be used by our tiny url application. It has definitions of 3 consul server, 3 etcd nodes, 3 cassandra instances, and 3 Kafka brokers]
  4. docker compose pull
  5. docker compose up
  6. In a new terminal:
       1. docker ps [In a new terminal, lists only the containers that are currently running]
       2. docker logs cassandra-1 [prints logs to std output]
       3. docker exec -it cassandra-1 /bin/sh [ log inside the container]
       4. nodetool status [prints cassandra status, in our case it will show that we have 3 nodes and it is up and running]
       5. cqlsh
       6. use dev;
       7. select \* from urls; [This will show an empty table in the beginning]
       8. exit;
       9. Stop the container
           1. docker stop cassandra-1 [ provide the name of the container you want to stop]
  7. cont+ c [ to stop all containers]
  8. docker compose down -v [claim all disk space, stops all containers, removes all named and anonymous volumes created by this compose file]
