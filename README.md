Questions
1. How did changing values on the SparkSession property parameters affect the throughput and latency of the data?

The latency affects throughput, since the execution of the next batch waits until the current batch is processed by the query
so this will affect the processedRowsPerSecond.

2. What were the 2-3 most efficient SparkSession property key/value pairs? Through testing multiple variations on values, how can you tell these were the most optimal?
To find the most optimal variation we can test multiple variations and see wish providing the largest possible value for processedRowsPerSecond.

To increase processedRowsPerSecond we can modify following settings:
spark.default.parallelism: total number of cores on all executor nodes.
spark.sql.shuffle.partitions: number of partitions to use when shuffling data for joins or aggregations.
spark.streaming.kafka.maxRatePerPartition: maximum rate at which data will be read from each Kafka partition.

