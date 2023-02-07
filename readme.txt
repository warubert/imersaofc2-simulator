//DOCKER GO
docker-compose up -d
docker-compose ps
docker exec -ti simulator bash

//COMANDOS EM GO
go mod init github.com/warubert/imersaofc2-simulator 
go build main.go
go run main.go
go get github.com/confluentinc/confluent-kafka-go/kafka

//DOCKER kafka
docker-compose up -d
docker exec -it kafka_kafka_1 bash

//COMANDOS kafka
kafka-consoconsumducer --bootstrap-server=localhost:9092 --topic=readtest
kafka-consoproducducer --bootstrap-server=localhost:9092 --topic=route.new-direction
kafka-consoconsumducer --bootstrap-server=localhost:9092 --topic=route.new-position --group=terminal
