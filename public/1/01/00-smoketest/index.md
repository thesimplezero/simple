# 

# Protohackers

In today's interconnected world, communication between devices and systems is essential. One of the fundamental protocols for communication over the internet is the Transmission Control Protocol (TCP), which allows for reliable, ordered, and error-checked delivery of data. In this blog post, we'll explore how to create a TCP Echo Service in Python, which is a simple server that echoes any data it receives back to the client. This is a useful exercise for understanding the basics of TCP communication and Python's socket programming.

Concepts Covered:
1. TCP Communication
2. Python's socket library
3. Threading in Python
4. Logging in Python
5. Exposing a local server to the internet using ngrok


## TCP Communication

TCP is a connection-oriented protocol, meaning it establishes a connection between two devices before exchanging data. The protocol ensures that the data is delivered reliably and in order, making it a popular choice for many applications, such as file transfers and email.

A TCP Echo Service is a server that listens for incoming TCP connections and echoes any received data back to the client unmodified. This service can be used to test network connectivity, debug applications, or as a building block for more complex systems.


## Python's Socket Library

Python's socket library provides a simple and efficient way to create TCP servers and clients. The library offers functions for creating, binding, listening, and accepting connections, as well as sending and receiving data over a socket.


To create a TCP server, you can follow these steps:


1. Create a socket using `socket.socket(socket.AF_INET, socket.SOCK_STREAM)`.
2. Bind the socket to a specific IP address and port using `bind((host, port))`.
3. Start listening for incoming connections using listen `(max_connections)`.
4. Accept new connections and handle them using `accept()`.


## Threading in Python

To handle multiple simultaneous clients, we can use Python's `threading` module. By spawning a new thread for each client connection, we can ensure that the server can efficiently process multiple connections concurrently.

To create a new thread for each connection, you can use `threading.Thread` class and pass in a function (in our case, the `handle_client` function) to be executed within the thread.


## Logging in Python

Logging is a crucial aspect of any application, as it helps you monitor and troubleshoot issues. Python's built-in `logging` module allows you to easily log messages at different severity levels, such as DEBUG, INFO, WARNING, ERROR, and CRITICAL. By configuring the logging module, you can store logs in a file, display them on the console, or even send them to a remote server for further analysis.


## Firewall Configuration

When exposing your server to the internet, it's important to configure a firewall to protect your system. We will configure the UFW firewall to allow incoming connections on port 7 (TCP) and deny all other incoming connections while allowing all outgoing connections.


`sudo ufw allow 7/tcp && sudo ufw enable`

## Exposing a Local Server to the Internet using ngrok

After configuring our firewall, we will expose our local server to the internet and for this task, will use ngrok. ngrok creates a secure public URL for your local server, which can be shared with clients to access your server from the internet.
