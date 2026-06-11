# Inter-LAN-Communication-Using-a-Router-in-GNS3
This project demonstrates basic Layer 3 routing in GNS3. Two separate LANs were created using switches and PCs. A Cisco router was configured with IP addresses on two interfaces to enable communication between the networks.IP addressing Default gateways Router interfaces Routing between networks Network connectivity testing using ping
## LAN 1 (192.168.1.0/24)

PC2 --------|
            |
PC3 --- Switch1 --- R1(F0/0)

                R1

LAN 2 (192.168.2.0/24)

PC4 --------|
            |
PC5 --- Switch2 --- R1(F0/1)

## IP Addressing Table
Device	Interface	IP Address	Subnet Mask
R1	FastEthernet0/0	192.168.1.1	255.255.255.0
R1	FastEthernet0/1	192.168.2.1	255.255.255.0
PC2	e0	192.168.1.2	255.255.255.0
PC3	e0	192.168.1.3	255.255.255.0
PC4	e0	192.168.2.2	255.255.255.0
PC5	e0	192.168.2.3	255.255.255.0


## Default Gateway
Network	Gateway
192.168.1.0/24	192.168.1.1
192.168.2.0/24	192.168.2.1

## Objectives
Configure IP addresses on router interfaces.
Configure IP addresses on PCs.
Establish communication between different networks.
Verify connectivity using ping commands.
Understand the role of routers in forwarding packets.

## Router Configuration
```
enable
configure terminal

interface fastethernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

interface fastethernet0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
exit

end
write memory
```
## PC Configuration
### PC2
```
ip 192.168.1.2/24 192.168.1.1
```
### PC3
```
ip 192.168.1.3/24 192.168.1.1
```
### PC4
```
ip 192.168.2.4/24 192.168.2.1
```
### PC5
```
ip 192.168.2.5/24 192.168.2.1
```
## Verification
Ping Router Gateway
```PC2> ping 192.168.1.1
```
### Result: Successful

### Ping Same Network

```PC5> ping 192.168.2.4
```
### Result: Successful

### Ping Different Network
```PC5> ping 192.168.1.3
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/040c06c0-40a5-4dfe-8473-ad48b36c744d" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7a9f604c-c789-4264-9829-e2979db4d45c" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fc3155e8-c5ca-4461-a32e-d94fe651ee41" />

### Result: Successful
The successful ping replies confirm that routing between the two LANs is functioning correctly.

## Key Concepts Learned
Router acts as a gateway between networks.
Devices in different subnets require a router to communicate.
Switches forward frames within a LAN.
Routers forward packets between LANs.
ICMP ping is used to test network connectivity.
Proper default gateway configuration is essential for inter-network communication.

## Skills Demonstrated
Cisco IOS Configuration
Basic Routing
IP Addressing
Network Troubleshooting
Connectivity Verification
GNS3 Simulation

## Conclusion
The project successfully established communication between two separate LANs using a Cisco router. All devices were able to communicate across networks, demonstrating the fundamental concept of routing and serving as a foundation for future CCNA and Network Security labs.
