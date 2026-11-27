# Day 3 — Computer Networks

**Topic:** Networking Fundamentals

---

## 1. What is a MAC address?

### Answer

A MAC address is the hardware address of a network card. It identifies that card on the local network.

- MAC means Media Access Control. The address is burned into the network card by the maker.
- It is 48 bits, written as six hex pairs, such as `3C:22:FB:A1:00:19`.
- A switch uses the MAC address to deliver a frame to the right device on the same LAN.
- It does not tell you which network the device belongs to. Moving a laptop to a new office does not change the card's MAC address.
- It works at the local link. A router does not use the MAC address to choose a path across the Internet.

### Interview

A MAC address is the permanent hardware address of a network interface. It is 48 bits, written in six hex pairs. Switches use it to deliver frames inside one local network. It identifies the device, not the network, so it stays the same when the device moves to another network.

#### Example

A laptop's Wi-Fi card has the MAC address `3C:22:FB:A1:00:19`. At home the router gives it the IP address `192.168.1.10`. At college it gets a different IP address. The MAC address on the card is still `3C:22:FB:A1:00:19`.

---

## 2. What is an IP address?

### Answer

An IP address is the logical address of a device on a network. Routers use it to send data to the right network and then to the right device.

- IP means Internet Protocol. The common version is IPv4, written as four numbers, such as `192.168.1.10`.
- It has two parts in practice: a network part and a host part. The network part says which network. The host part says which device on that network.
- Unlike a MAC address, an IP address can change. A home router often assigns it automatically with DHCP.
- Routers forward packets by IP address. Switches deliver frames by MAC address.
- IPv4 is 32 bits. IPv6 is the newer 128-bit form, written with hex groups, because the world ran short of IPv4 addresses.

### Interview

An IP address identifies a device on a network so routers can deliver data to it. An IPv4 address looks like `192.168.1.10`. Part of it names the network and part names the device. It can change when you join another network. A MAC address is the hardware address used inside one local network. An IP address is the logical address used to move packets between networks.

#### Example

Ali's phone is `192.168.1.20` on the home Wi-Fi. The router is `192.168.1.1`. A packet for the phone arrives at the router, and the router uses `192.168.1.20` to hand it to that phone. At a cafe, the phone is given a new IP address. Its MAC address does not change.
