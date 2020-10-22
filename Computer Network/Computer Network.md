# Computer Network

### 1.1 Router Advertisement
![](https://i.imgur.com/aUwC3jw.png)

### 1.2 Router Solication
![](https://i.imgur.com/o5TC11y.png)

### Prefix Information Option in solication
![](https://i.imgur.com/5oR5fV5.png)

> set a preferred lifetime
> preferred lifetime vs valid lifetime?

### MTU option

### Link layer address option
![](https://i.imgur.com/uZLeR0X.png)

### 1.3 ICMP redirect?
![](https://i.imgur.com/VnxKtdj.png)
* in the link 
* shorter path than original path
> example 1
> Host and two routers, G1 and G2, are connected to shared Ethernet segment and have IP addresses in the same network 10.0.0.0/24

1. Gateway G1 with IP address 10.0.0.1 receives data packet from host 10.0.0.100 on a network to which it is attached.

2. The gateway, G1, checks its routing table and obtains the IP address 10.0.0.2 of the next gateway, G2, on the route to the data packet's destination network, X.

3. If G2 and the host identified by the source address of IP packet are on the same network, ICMP Redirect message is sent to the host. The ICMP Redirect message advises the host to send its traffic for network X directly to gateway G2 as this is a shorter path to the destination.

4.  The gateway G1 forwards the original data packet to its destination.



![](https://i.imgur.com/YPbEQOA.png)


### 1.4 Duplicated address detection(DAD)
![](https://i.imgur.com/qOhXVe2.png)

