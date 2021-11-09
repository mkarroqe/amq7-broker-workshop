# Lab 3. Running a Broker Instance

## Run the broker in interactive mode

1. Once the broker is created, navigate to the `mybroker` instance `bin` folder if not already there

   ```sh
   $ cd instances/mybroker/bin
   ```

1. Run the `artemis` script to start the broker in interactive mode

   ```sh
   $ ./artemis run
   ```

The broker will produce output similar to the following:

```sh
...
INFO  | main | Initialized dispatch-hawtio-console plugin
23:54:24,475 INFO  [org.apache.activemq.artemis] AMQ241001: HTTP Server started at http://localhost:8161
23:54:24,475 INFO  [org.apache.activemq.artemis] AMQ241002: Artemis Jolokia REST API available at http://localhost:8161/jolokia
```

## Test the broker with the CLI

1. In a separate terminal/console run the artemis command to consume from the default address

   ```sh
   $ ./artemis consumer
   ```
   
   ```bash
   bin % ./artemis consumer
   Connection brokerURL = tcp://localhost:61616
   Consumer:: filter = null
   Consumer ActiveMQQueue[TEST], thread=0 wait until 1000 messages are consumed
   Received 1000
   Consumer ActiveMQQueue[TEST], thread=0 Consumed: 1000 messages
   Consumer ActiveMQQueue[TEST], thread=0 Elapsed time in second : 88 s
   Consumer ActiveMQQueue[TEST], thread=0 Elapsed time in milli second : 88300 milli seconds
   Consumer ActiveMQQueue[TEST], thread=0 Consumed: 1000 messages
   Consumer ActiveMQQueue[TEST], thread=0 Consumer thread finished
   ```

1. In another terminal/console do the same but this time to produce messages to the same default address

   ```sh
   $ ./artemis producer
   ```

   >  *You will see the producer sending 1000 messages, and the same amount, received by the consumer.*
      
      ```bash
      bin % ./artemis producer
      Connection brokerURL = tcp://localhost:61616
      Producer ActiveMQQueue[TEST], thread=0 Started to calculate elapsed time ...

      Producer ActiveMQQueue[TEST], thread=0 Produced: 1000 messages
      Producer ActiveMQQueue[TEST], thread=0 Elapsed time in second : 40 s
      Producer ActiveMQQueue[TEST], thread=0 Elapsed time in milli second : 40558 milli seconds
      ```

## Management console

1. To access the management web console, open a browser and goto http://localhost:8161/hawtio/login
1. Log in to the console using the username/password entered when the AMQ 7 instance was created.

   > In this case is `admin`/`admin`

## Running as a Service (Optional)

If you want to run the broker in background as a system service you can use the provided script to archive it.

* For Linux/Unix

```sh
./artemis-service start
```

* For Windows

```sh
./artemis-service.exe start
```

*Remember to shut down the running instance before starting the service*

End of Lab 3.
