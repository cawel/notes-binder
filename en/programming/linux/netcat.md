# netcat

Run the netcat chat server on localhost (127.0.0.1) port 10001:
```
  nc -n -v -l -p 10001
```

-n tells netcat not to do DNS lookup. Use this if you are using IPs only. It takes a long time for the DNS to timeout. If you are using hostnames, leave this switch off.
-v tells netcat to be verbose. This will allow you to see the chat messages in the terminal on the server.
-l tells netcat to listen for connections on the localhost. This will allow other nodes to connect to your chat server.
-p 10001 tells netcat what port to listen on. Again, make sure that you open the port on your firewall. This can be anything, but make it obscure and not a standard port.

Now lets say Bob wants to chat with you on your new netcat chat server. It is very easy for him to connect and talk with you.

```
nc -n -v 192.168.10.1 10001
```
