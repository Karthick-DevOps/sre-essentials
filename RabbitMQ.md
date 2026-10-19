## Rabbitmq core concepts and architecture:

Producer  
Consumer  
Queue  
Exchange  
Binding  
Routingkey  
Message  


## AMQP: Advanced Message Queuing Protocol
Message Queue:  
	* allows applications to communicate by sending messages to each other  
	* provides temporary message storage when destination program is busy or not connected  
	* is made up of producer, message broker( the message queue software), and a consumer  
	* provides asynchronous communication between producer and consumer  

## RabbitMQ:
	* a message queue software (message broker/queue manager) that acts an an intermediatary platform where different applications can send and receive messages
	* originally supports  AMQP but not serveral other protocols such as STOMP,MQTT and HTTP.
	
	
	Producer ---------------> Exchange ------> RabbitMQ Broker -----> Queue -----> Consumer

**Producer**
	An application that sends messages to rabbitmq broker
**Consumer**
	An application that reads messages from the rabbitmq broker
**Queue**
	A buffer or a storage in rabbitmq broker to store messages
		* messages are put into queue by producer and read from it by consumer
		* once a message is read, it is consumed and removed from the queue
		* a message can thus only be processed exactly once
		* N number of queues can be created in a broker
**Message**: 
	Information that is sent from the producer to a consumer throught RabbitMQ
	Message can be	
			* string
			* plain text
			* json
			* byte array
			* HTML
**Exchange**
		* Acts an an intermediary between producer and queue
		* instead of sending message directly to a queue , a producer can send them to an exchange instead
		* the exchange then sends those messages to one or more queues following a specified set of rules
		* => prodcuer does not need to know the queues that eventually receive those messages (need to verify)
**Routing Key** is a key that the exchange looks at to decide how to route the message to queues
		* routing key is address of the message
**Binding**
	A binding is a link between queue and an exchange


