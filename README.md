_This project has been created as part of the 42 curriculum by atahiri-._

# NetPractice

## Description:

**Net Practice** is a networking project aimed at understanding subnetting in a practical hands-on experience.  
The goal is to make the user comfortable with networking fundamentals especially subnetting.  
It uses a network simluation program in which the user has to give the correct ip adresse and subnet mask for each device.  

## Instructions:

### Installation:

download the `net_practice.1.9.tgz` file and extract it using the following command:

```bash
tar -xzf net_practice.1.9.tgz
```

It will produce a directory called `net_practice/`.

### Running the interface:

To run net practice, simply excute the file `run.sh`

```bash
./run.sh
```

Now you can open your browser and navigate to [`http://0.0.0.0:49152/`](http://0.0.0.0:49152/).

### Training & Evaluation:

Once you open the website, you'll have two modes to choose from, **training mode** or **evaluation mode**.

* In _Training Mode_ you can practice a total of 10 subnetting exercises, once you solve one you'll have to solve a harder one.
* In _Evaluation Mode_ you'll receive 3 random exercises from ranges 6-10 to solve.

In order to pass a level you have to fill the ip/subnet boxes with correct values demonstaring good understanding of subnetting concenpts.

### Exporting Configuration:

In each level you can export the configuration json file by simply pressing the **Get my config** button.
The following are the correct configurations for all the levels:


1. [level1.json](level1.json)
2. [level2.json](level2.json)
3. [level3.json](level3.json)
4. [level4.json](level4.json)
5. [level5.json](level5.json)
6. [level6.json](level6.json)
7. [level7.json](level7.json)
8. [level8.json](level8.json)
9. [level9.json](level9.json)
10. [level10.json](level10.json)

## Resources:

### References:

The following are some resouces that were of immese help in this project:

* [**Subnetipv4**](https://subnetipv4.com/): a really helpful website to practice subnetting.
* [**NetworkChuck's Free CCNA playlist**](https://www.youtube.com/watch?v=S7MNX_UD7vY&list=PLIhvC56v63IJVXv0GJcl9vO5Z6znCVb1P): very comprehensive networking series, and really enjoyable to watch.
* [**NetworkChunk's You Suck at Subnetting playlist**](https://www.youtube.com/results?search_query=network+chunk+subnetting): playlist by network chuck too, but focused on subnetting.
* [**BenEater's Networking series**](https://www.youtube.com/watch?v=XaGXPObx2Gs&list=PLowKtXNTBypH19whXTVoG3oKSuOcw_XeW): dives into the lowest levels of networking down to the electricity in the wires.

### AI Usage:

AI was rarely used in this project, the usages were limited to:

* Explaining very novel networking concepts in a general view.
* Demonstrating some subnetting examples.
* Fixing typos in documentation.

### Networking Concepts:

#### TCP/IP Addressing

An **IP address** identifies a device/interface on a network.

Example:

```text
192.168.1.10
```

* **IPv4** → 32-bit address, usually written as 4 numbers.
* **IPv6** → 128-bit address, designed for a much larger address space.
* An IP address identifies **where** a device is on a network.

Example:

```text
PC       → 192.168.1.10
Server   → 192.168.1.20
Router   → 192.168.1.1
```

---

#### Subnet Masks

A **subnet mask** tells you which part of an IP address represents the **network** and which part represents the **host**.

Example:

```text
IP:          192.168.1.10
Subnet mask: 255.255.255.0
CIDR:        /24
```

This means:

```text
Network: 192.168.1.0
Host:    .10
```

So devices such as:

```text
192.168.1.10
192.168.1.20
192.168.1.50
```

are on the same subnet.

---

#### Default Gateway

The **default gateway** is usually your router's IP address on your local network.

It is where a device sends packets when the destination **isn't on its own subnet**.

Example:

```text
PC:      192.168.1.10
Gateway: 192.168.1.1
Internet: somewhere else
```

The PC effectively says:

> "This destination isn't local, so I'll send the packet to my gateway."

---

#### Switches

A **switch** connects devices within a local network (**LAN**).

It primarily works with **MAC addresses**.

```text
PC ──┐
PC ──┼── Switch
PC ──┘
```

The switch learns which MAC address is connected to which port and forwards Ethernet frames accordingly.

> Switch = connects devices inside a network.

---

#### Routers

A **router** connects **different networks** and forwards packets based on IP addresses.

```text
LAN A ── Router ── LAN B
                 │
              Internet
```

For example:

```text
192.168.1.0/24
       ↓
    Router
       ↓
10.0.0.0/24
```

**Think:**

> Router = connects networks.

---

#### OSI Model

The **OSI model** divides networking into 7 conceptual layers:

| Layer | Name         | Main idea                         |
| ----- | ------------ | --------------------------------- |
| 7     | Application  | HTTP, DNS, FTP                    |
| 6     | Presentation | Encoding, encryption, formatting  |
| 5     | Session      | Manages communication sessions    |
| 4     | Transport    | TCP, UDP, ports                   |
| 3     | Network      | IP, routing                       |
| 2     | Data Link    | Ethernet, MAC addresses, switches |
| 1     | Physical     | Cables, radio, electrical signals |

A simple way to remember the important networking layers:

```text
L7  Application   → HTTP
L4  Transport     → TCP / UDP
L3  Network       → IP / Router
L2  Data Link     → Ethernet / MAC / Switch
L1  Physical      → Cable / Wi-Fi signal
```

