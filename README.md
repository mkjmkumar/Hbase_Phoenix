Hbase Table/Truck is Collection of type of containers.
Each Table/Truck is made up of different components loading parts where its container made of different containers/Column Family (CF). Each container of truck has Column Qualifier (CQ) or columns or sections.



																																																																																																																																																																																																																																																																																																																																																																																																											
Phoenix Performance Tuning Tips:-
1.	HDFS Short-Circuit Local Reads
Background: - In HDFS, reads normally go through the DataNode. Thus, when the client asks the DataNode to read a file, the DataNode reads that file off of the disk and sends the data to the client over a TCP socket. So-called “short-circuit” reads bypass the DataNode, allowing the client to read the file directly. Obviously, this is only possible in cases where the client is co-located with the data. Short-circuit reads provide a substantial performance boost to many applications.
	  HDFS>dfs.client.read.shortcircuit>True
	  HDFS>dfs.client.read.shortcircuit.streams.cache.size>4096

Ambari-Metrices>Advanced ams-hbase-site> dfs.client.read.shortcircuit>True

Average percentage of local files to RegionServer mean
That's the ratio of HFiles associated with regions served by an RS having one replica stored on the local Data Node in HDFS. RS can access local files directly from a local disk if short-circuit is enabled. And If you, for example run a RS on a machine without DN, its locality will be zero. You can find more details here. And on HBase Web UI page you can find locality per table.
 

2.																																																		
