# Day 2 — Computer Networks

**Topic:** Networking Fundamentals

---

## 1. What is network topology? Explain star, bus, ring, and mesh.

### Answer

Network topology is the shape of the network: how the devices are connected to each other.

- **Star:** every device connects to one central switch. One broken cable affects only that device. If the center fails, the whole network stops. This is the common office and home layout.
- **Bus:** every device shares one main cable. It is simple and cheap. If that main cable breaks, the whole network stops.
- **Ring:** each device connects to the next one, making a circle. Data passes from device to device around the ring. One break can stop the circle.
- **Mesh:** devices have many links between them. Full mesh means every device connects to every other device. Partial mesh means only some extra links exist. More paths means the network still works if one link fails. It costs more cable.
- Memory line: star is one center, bus is one cable, ring is a circle, mesh is many paths.

### Interview

Network topology is the way devices are arranged and connected. In a star, every device connects to one central switch, which is what most offices use. In a bus, every device shares one main cable. In a ring, each device connects to the next and the data travels around the circle. In a mesh, there are many paths between devices, so one broken link does not stop the network. Mesh costs more because it needs more connections.

#### Example

An office where every computer cable goes into one switch is a star. An old setup where all computers clip onto one long cable is a bus. Four computers, each joined only to the next until the last joins the first, is a ring. A company with several links between its sites, so traffic can take another path when one link is down, is a mesh.

---

## 2. Difference between a hub, switch, and router.

### Answer

A hub, a switch, and a router all connect devices, but each one makes a smarter choice about where the data goes.

- **Hub:** the simplest device. It copies incoming data to every port. It does not check who the data is for. Everyone on the hub hears the traffic.
- **Switch:** used inside one local network. It learns the MAC address of the device on each port and sends the data only to that device.
- **Router:** connects different networks. It reads the IP address and chooses the path toward the destination. A home router joins the home network to the Internet.
- Memory line: a hub shouts to everyone, a switch delivers inside one network by MAC address, a router sends between networks by IP address.
- A home "Wi-Fi router" is often a router, a switch, and a wireless access point in one box. In an interview, explain the three jobs separately.

### Interview

A hub repeats incoming data out of every port, so every connected device receives it. A switch is smarter: it learns MAC addresses and forwards the frame only to the correct device inside the same network. A router connects separate networks and forwards packets by IP address, which is how a home or office network reaches the Internet. The hub shares everything, the switch delivers inside the LAN, and the router moves traffic between networks.

#### Example

In an old lab, a hub sends one student's file to every computer on the table. A switch in an office sends that file only to the computer it is addressed to. The office router then sends internet traffic from that network out to the ISP, and brings replies back to the right network.

---
