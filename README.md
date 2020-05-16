# KafkaTrainDashboard

## Description

A dashboard displaying system status for train commuters, using Kafka and ecosystem tools like REST Proxy and Kafka Connect to accomplish this task. [Credit: https://www.udacity.com/course/data-streaming-nanodegree--nd029]

### Step 1 - Kafka Producers

Developing steps:

1. [Add fundamental Producer functions](https://github.com/jadugnap/KafkaTrainDashboard/commit/4231f8a1f30f57daf9f71615875942e1c8474050 "link to this commit")
2. [Define arrival.value schema](https://github.com/jadugnap/KafkaTrainDashboard/commit/d1f52ad1fce37e29776965a726a9eebc6ffb7a6a "link to this commit")
-- no `enum` type due to [Object of type mappingproxy is not JSON serializable](https://github.com/confluentinc/confluent-kafka-python/issues/610) issue.
3. [Enable Station to produce message for each arrival event](https://github.com/jadugnap/KafkaTrainDashboard/commit/98c0ffaca1c380fad86f8c36e55869b6adaba7a0 "link to this commit")
-- note the presence multiple station_id(s) for each station_name.
4. [Define turnstile.value schema](https://github.com/jadugnap/KafkaTrainDashboard/commit/770961e25442a5ac9c8dcfe0b7baca878fe8283a "link to this commit")
5. [Enable Turnstile to produce message for each rider entrance in each station_name](https://github.com/jadugnap/KafkaTrainDashboard/commit/56be32c9c29ba33634ec516909b539960f13769f "link to this commit")

Testing steps:

1. To produce -> `cd producer` -> `python simulation.py`
2. To consume -> `kafka-avro-console-consumer --bootstrap-server PLAINTEXT://localhost:9092 --whitelist ".*event"`
