## REFLECTION
1. **what is amqp?**
> AMQP is an open standard application layer protocol for passing messages between applications and systems, regardless of message broker vendor or platform. It defines rules and message capabilities which must be made available by an AMQP compliant implementation (for example: RabbitMQ) to follow the AMQ Model.
2. **what it means? guest:guest@localhost:5672, what is the first guest, and what is the second guest, and what is localhost:5672 is for?**
> guest:guest@localhost:5672 is the connection string for the RabbitMQ server. guest:guest refers to the username and password (username:password) for the server, while localhost:5672 is the address of the server itself.
<br>

### **Screenshot of RabbitMQ, simulating a slow subscriber.**
> Total number of queues went up to twenty, after running cargo run the publisher console five times (sending five messages per run). Hence, twenty messages in queue. <br><br>
![alt text](images/slow_rabbitMQ.png) <br><br>

### **Running three subscriber console instances.**
> Console 1. <br><br>
![alt text](images/subscriber1.png) <br><br>
> Console 2. <br><br>
![alt text](images/subscriber2.png) <br><br>
> Console 3. <br><br>
![alt text](images/subscriber3.png) <br><br>

### **Screenshot of RabbitMQ spike reduced because of the extra instances taking up the requests in the queues.**
![alt text](images/mult_rabbitMQ.png) <br><br>

> One improvement that could be proposed is to replace "unwrap()" for errors. While it is quick and useful in some cases, it is only meant to be a placeholder. It provides zero information for error-handling and simply just crashes the program, which could be problematic. Better implementation would be using "match" which gives us more explicit control on error-handling and avoids panic!s if it is not needed.