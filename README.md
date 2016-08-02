# MIP - quickly display IP addresses

mip and mip6 are bash fonctions using "ip address show", "ip route" and "ip netns" commands to display the currently defined netns, ip addresses and default outgoing interface.

## Usage

```
$ . ./mip
$ mip
NS: Current
	lo:          127.0.0.1     /8
	[enp3s0f1]:  10.37.169.80  /24
	vboxnet0:    192.168.56.1  /24
	docker0:     172.17.0.1    /16
$ mip6
NS: Current
	lo:          ::1                        /128
	[enp3s0f1]:  fe80::82fa:5bff:fe01:ff7b  /64
	vboxnet0:    fe80::800:27ff:fe00:0      /64
	docker0:     fe80::42:e3ff:fe57:8a17    /64

```

mip displays the currently affected ip addresses in each network namespace and emphase the interface used to reach to default gateway
mip6 does the same thing with ipv6 addresses.

## Story

I wrote them because "ip address show" output is not very readable for me (i have to search for the IP addresses in the output).
I added netns support when messing around with some SDN implementation.


IP addresses and network masks are separated with a space in a copypasta frendly way.
