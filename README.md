# confluent-event-sourcing
To test the queries for KSQLDB, feel free to use terraform resources from below repo to get started quickly:
[Confluent Terraform Deploy](https://github.com/Satej/confluent-kafka-terraform)

1. In the KSQLDB interface, make sure to have below two properties.

`auto.offset.reset = Earliest`
`ksql.streams.commit.interval.ms = 3000`

2. Create stream to hold shopping cart events.

```sql
CREATE STREAM shopping_cart_events (customer VARCHAR, item VARCHAR, qty INT)
WITH (kafka_topic='shopping_cart_events', value_format='json', partitions=1);
```

![Create Shopping Cart Stream](./1-create-stream-shopping-carts-events.png)
