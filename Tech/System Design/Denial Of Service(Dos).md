A Denial of service attack is an attempt to break a system such as a server, network, API, such that it is unavailable to actual/legitimate users . The attacker usually isnt trying to steal anything , his goal is to exhaust the system such that it is unavailable to others 

Every system has limited resources like : [[network bandwidth]], CPU , memory, [[file descriptors]], database connections and so on . A DoS attack consumes one of these resources until they run out and arent available for others to use .

**A technical example: the SYN flood.** TCP uses a three-way handshake. The client sends SYN, the server replies SYN-ACK, and the client sends ACK. When the server receives a SYN, it allocates an entry in its _half-open connection queue_ and waits for the final ACK. An attacker sends thousands of SYN packets per second, often with spoofed source IPs, and never sends the ACK. The queue fills with half-open connections, and new legitimate SYNs are dropped. The server is still running, but nobody can connect.

[[Distributed Denial of Service (DDoS)]]
A DDos attack is the same idea , except the traffic comes from not one machine, but many machines at once, typically thousands to millions of them. 

A single attacker machine has limited bandwidth. It is also easy to block: you see one IP sending garbage and you firewall it. DDoS solves both problems for the attacker.

1. **Scale.** A million devices sending 1 Mbps each adds up to 1 Tbps, far more than most data centers can absorb.
2. **Hard to filter.** The traffic comes from IPs all over the world that look like ordinary home connections, so you can't block "the attacker."

The machines are usually part of a botnet(computers, cameras, routers and other devices infected with malware and controlled remotely by the attacker through a command and control(C2) server.

**A real example: the Mirai botnet and the Dyn attack (2016).** Mirai malware scanned the internet for IoT devices such as cameras, DVRs, and routers that still used factory-default passwords like `admin/admin`. It infected hundreds of thousands of them. In October 2016 the botnet flooded Dyn, a major DNS provider. Because Dyn resolved domain names for services like Twitter, Netflix, Reddit, GitHub, and Spotify, those sites became unreachable for large parts of the US. None of those companies was attacked directly; their DNS dependency was the weak point.
   
   

