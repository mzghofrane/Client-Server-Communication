# Client-Server-Communication
The architecture of this system corresponds to the following general diagram: 
A server waits for questions from clients in a pipe named fifo1. 
A question corresponds to the request to send n numbers drawn at random by the server (n is a random number between 1 and NMAX drawn at random by the client). 
In its question, the client also sends its number so that the server can wake it up via the SIGUSR1 signal when it has entered the answer. 
Several clients may be waiting for a response in the same tube named fifo2.
It is necessary to define a protocol ensuring that each client reads the responses intended for it. 
The client notifies the server with this same signal when it has read the responses.
