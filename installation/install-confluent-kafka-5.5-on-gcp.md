Install Confluent Server 5.5 on a Single Node
================================

#### Install Confluent Kafka using below commands:
```bash
wget -qO - https://packages.confluent.io/rpm/5.5/archive.key | sudo apt-key add -
sudo add-apt-repository "deb https://packages.confluent.io/deb/5.5 stable main"
sudo apt-get update
sudo apt-get install confluent-server
```

#### Give 777 permission to /var/lib/zookeeper
```bash
sudo chmod -R 777 /var/lib/zookeeper
```

#### Start the Zookeeper Services:
```bash
sudo systemctl start confluent-zookeeper
```
**Note:** If you are facing issue while starting zookeeper
Open myid file and specify ``0`` in it (remove the existing id)
```bash
sudo vi /var/lib/zookeeper/myid
```
 
### Restart the Zookeeper Services: 
```bash
sudo systemctl restart confluent-zookeeper
```

### Check the status of Zookeeper Services: 
```bash
sudo systemctl status confluent-zookeeper
```

#### Start Confluent server
```bash
sudo systemctl start confluent-server.service
```
     Start Schema Registry
sudo systemctl start confluent-schema-registry

     Start other Confluent Platform components as desired.
sudo systemctl start confluent-control-center
sudo systemctl status confluent-control-center

sudo systemctl start confluent-kafka-rest
sudo systemctl status confluent-kafka-rest

sudo systemctl start confluent-kafka-connect
sudo systemctl status confluent-kafka-connect

sudo systemctl start confluent-ksqldb
sudo systemctl status confluent-ksqldb



