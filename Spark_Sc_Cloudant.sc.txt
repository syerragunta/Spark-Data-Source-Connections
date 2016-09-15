
val sqlContext = new org.apache.spark.sql.SQLContext(sc)

val cloudantdata = sqlContext.read.format("com.cloudant.spark").
option("cloudant.host","ffdc4b81-d764-46be-8e47-03f491d7b5ae-bluemix.cloudant.com").
option("cloudant.username", "ffdc4b81-d764-46be-8e47-03f491d7b5ae-bluemix").
option("cloudant.password", "80dfbcf49b67682d06b06cafc38b68b19c00c994275c81a071506f513a78ed26").
load("crimes")

cloudantdata.printSchema

cloudantdata.count()
