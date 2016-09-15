
val sqlContext = new org.apache.spark.sql.SQLContext(sc)

val dashdata = sqlContext.load("jdbc", Map( "url" -> "jdbc:db2://dashdb-entry-yp-dal09-10.services.dal.bluemix.net:50000/BLUDB:user=dash6718;password=yfrZsCQTr6Hj;",  "dbtable" -> "AUCTION_SALE_DATA"))

dashdata.registerTempTable("AUCTION_SALE_DATA")

dashdata.printSchema

dashdata.collect

val results = sqlContext.sql("SELECT LI_SALE_NUMBER from AUCTION_SALE_DATA")

results.collect


