# flume-mysql-sink
Logs collected by Flume1.6.0 are stored in the MySQL database

### mysqlSink.conf
---
     agent1.sources = source1
     agent1.sinks = mysqlSink
     agent1.channels = channel1



     agent1.sources.source1. type  =  exec
     agent1.sources.source1. command  = tail -F /Work/flum-1.6/tail_log_exec
     agent1.sources.source1.channels = channel1



     agent1.sinks.mysqlSink. type  = org.flume.mysql.sink.MysqlSink
     agent1.sinks.mysqlSink. hostname =localhost
     agent1.sinks.mysqlSink.port=3306
     agent1.sinks.mysqlSink.databaseName=sinktest
     agent1.sinks.mysqlSink.tableName=mysqltest
     agent1.sinks.mysqlSink.user=root
     agent1.sinks.mysqlSink.password=root
     agent1.sinks.mysqlSink.channel = channel1


     agent1.channels.channel1. type  =  memory
     agent1.channels.channel1.capacity = 1000
     agent1.channels.channel1.transactionCapactiy = 100
