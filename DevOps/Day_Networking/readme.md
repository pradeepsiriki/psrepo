Do you know how the request from ur laptop to the website and fetch it to your machine

let's learn few basic things

Ip address: unique address for the device
    - standards are ipv4 and ipv6
    - ipv4 looks 172.16.3.4 for example
    - let's decode the 4 bytes( 32 bits total) , they are (0-255.0-.255.0-255.0-255)
    - do some exercise to convert into bit , try it for better understanding

Subnet: out of a complete network, we can seggreate them to finance, hr, inventory, payments etc
    - risk is only limited to only one subnet if at all if you wnat to take chance, but others are safe
    - helps leveraging what is needed and not to waste all the rest
    - try to create subnet for your home wifi

public subnet: can access to internet
private subnet: can NOT access to internet

Let's learn more on vpc, routing table, Internet gateway when we want to access internet via public subnet
whenever you are creating the subnet, you will be working on cidr (how many ip address should be assgined to a subnet)

CIDR:
    - AWS - > vpc =- > subnet -> CIDR (172.16.13.2/24)
    - let's say if your ip addressrange is 172.16.0.0 to 172.16.255.255 and you want to create a subnet for just 255 hosts , all  that you need is 172.16.0.0 to 172.16.0.255 (first 3 are common (host network), the last portion varies), this is when you want to mention cidr as 172.16.0.0/24
    - now tell me, if you want to put finnce subnet only two ips, how do you give cidr (172.16.0.0/31)
    - now the calculation, it is always going to be 32 (total) - 31 (the cidr) = 1 => now put 2 power 1 ==> 2 ips
    - nowif you need 32 ips  , that means 2 power 5, so give (32- 5) = /27
    - 10.0.0.0/8 means => 8+24= 32, so it gets 2 power 24 
    - /8 are class A,
    - /16 are class B, 
    - /24 are class C
    - the more the /<number>, the less the ips you get and vice versa

what is public ips: they are constant and wont change, we cant apply the cidr on public ip address range

Ports:
    - don't take any popular ports like 22, 8000, 8080 as they are already used by some popular apps