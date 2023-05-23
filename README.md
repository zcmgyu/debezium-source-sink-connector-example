


$ docker compose up

$ curl -s -X GET "http://localhost:8083" | jq '.'

$ curl -i -X POST -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/ -d @source.json

$ curl -i -X POST -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/ -d @sink.json

$ curl -s -X GET "http://localhost:8083/connectors" | jq '.'


[
  "inventory-customers-source-connector",
  "sink-customers-sink-connector"
]

$ curl -s -X GET "http://localhost:8083/connectors/inventory-customers-source-connector/topics" | jq '.'

$ curl -s -X GET "http://localhost:8083/connectors/sink-customers-sink-connectorr/topics" | jq '.'


$ docker run -it --rm --name mysqlterm --network debezium-source-sink-connnector-examples_default --link debezium-source-sink-connnector-examples-mysql-1 --rm mysql:8.0 sh -c 'exec mysql -h"$MYSQL_PORT_3306_TCP_ADDR" -P"$MYSQL_PORT_3306_TCP_PORT" -uroot -p"$MYSQL_ENV_MYSQL_ROOT_PASSWORD"'

$ CREATE TABLE sink.customers LIKE inventory.customers;
