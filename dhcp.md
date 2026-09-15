## DHCP (Dynamic Host Configuration Protocol)

![Image](https://images.openai.com/static-rsc-4/KVLPicnaECx-mz8NrWBSzhd5CmZNHh4SBJHN-0JBoWasIIvNpz1FLQL_G-xbIRmDCfubR3hl2kaOQ6kkKuDZr2yIvslnUzke160zYXdajgbsi3y33bQV45A5cruypJeJcYfaOUtyKnmMpg5X1EGFNF75kEPjf-CKQLJHyGWC-kfq6vl7BwY3KKlzV8mMyv2o?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/kSAvtHFATtPX4AFEsJQAmTw3asO2QP9tygSkCXcEZul__JF0yepCKjbW67la_ikt7fx14uQFZpcZeswT-K4_0hIV1PvNX1NwTISkEIA8_4ohGng4NUdfSWN53pWgzyoLlg3DFpmV36TqEfTSg03GgfJ8HgWxiyABXDcGyECyUjjnP2WTxb0Fs6LRjFRizFd5?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/4u35NgvK6A9_365ZATGT2kKAS_lU6KKRl9QtyBVyPQMGsaThVGmXoROi-gx1bLbWRQMEUL85xpeRSC2dEyu_gUyLm7eWMstJLc9PkRt7i5Wy791FbmRJinWYDfshfQu_4o3fGH20VjplnX1c-hLWoW3cONkjdYcWTAtRbAtesp0f67r2Xz67CAQJ8GzQrhwS?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/j0NLuBaG2Dy3O0KYlhBWk2paj5_Lp8tstgAEViPU7pr5rQl74g5fZXeXBglL1eZ6Y_rWIXjbQpV-pstf1HUhGAE2n4UuvUIn9NngLAuepEoKE7lKnCthmlYj5m3Ed59NGjRzvdR7jcnl-muhouJQNPUfo_tgJsIarkf97ciywDF9WyI3xxDSNbuJJ30bYAG3?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/cQq0KSCmTUbatLXN2ddIar0LkybDfCQO-1SHPKcsciIbHQ-GMY4uScpAcKFVq-Si_BUYyKMly5XA7ij8zjD9LJ4XwXVRt_u5gkZNWxUkhA9hOzCvdr9mm-P27kZKgTtZQveO24FGYrFjpa-xRCC3yu-rp-VOjXHThF-CTn4E2JZmBBjVc1QdifISyzR0RxE4?purpose=fullsize)

**DHCP** stands for **Dynamic Host Configuration Protocol**. It is a network protocol that **automatically provides devices with the network configuration they need to communicate on a network**.

Instead of manually configuring an IP address, subnet mask, gateway, and DNS on every laptop or computer, DHCP allows a **DHCP server** to provide these settings automatically.

### 1. What does DHCP provide?

A DHCP server can provide:

* **IP address** → identifies the device on the network
* **Subnet mask** → defines the local network
* **Default gateway** → tells the device where to send traffic outside its subnet
* **DNS server** → allows domain-name resolution
* **Lease time** → determines how long the device can use the assigned IP
* Other options such as domain name, NTP server, etc.

For example:

```text
Laptop
IP Address:     192.168.10.105
Subnet Mask:    255.255.255.0
Gateway:        192.168.10.1
DNS:            8.8.8.8
Lease:          8 hours
```

The laptop can receive all of this from DHCP automatically.

---

## 2. How DHCP works: DORA

The basic DHCP process is called **DORA**:

**D → Discover**
**O → Offer**
**R → Request**
**A → Acknowledge**

```text
DHCP Client                         DHCP Server
     |                                   |
     | ---- DHCP Discover -------------> |
     |                                   |
     | <---- DHCP Offer ---------------- |
     |                                   |
     | ---- DHCP Request --------------> |
     |                                   |
     | <---- DHCP ACK ------------------ |
     |                                   |
     |       IP configuration            |
```

### Step 1: DHCP Discover

When a device joins the network, it doesn't initially know which DHCP server is available.

It broadcasts a **DHCP Discover** message.

```text
Client → "Is there any DHCP server available?"
```

### Step 2: DHCP Offer

A DHCP server receives the Discover and offers an available IP address.

```text
Server → "You can use 192.168.10.105"
```

The offer can also contain the subnet mask, gateway, DNS, lease time, etc.

### Step 3: DHCP Request

The client selects an offer and requests that IP address.

```text
Client → "I want 192.168.10.105"
```

### Step 4: DHCP ACK

The server confirms the assignment.

```text
Server → "Approved. You can use 192.168.10.105"
```

The client configures its network interface and can communicate normally.

---

# 3. DHCP uses UDP

DHCP normally uses **UDP**, not TCP.

| Communication |       Port |
| ------------- | ---------: |
| DHCP Server   | UDP **67** |
| DHCP Client   | UDP **68** |

So:

```text
DHCP Client                    DHCP Server
UDP 68        ←→              UDP 67
```

This is important when configuring firewalls and troubleshooting DHCP.

---

# 4. DHCP Lease

DHCP usually doesn't give an IP address to a device permanently.

Instead, the address is given for a **lease period**.

For example:

```text
IP: 192.168.10.105
Lease: 8 hours
```

Before the lease expires, the client attempts to renew it.

If the device leaves the network permanently, the address can eventually become available for another device.

This allows organizations to efficiently manage a limited pool of IP addresses.

---

# 5. DHCP IP Pool

A DHCP server normally has a range of addresses that it can distribute.

For example:

```text
Network: 192.168.10.0/24

DHCP Pool:
192.168.10.100
      ↓
192.168.10.200
```

So devices may receive:

```text
Laptop 1 → 192.168.10.100
Laptop 2 → 192.168.10.101
Laptop 3 → 192.168.10.102
...
```

Addresses outside the pool can be reserved for infrastructure such as routers, servers, switches, or printers.

---

# 6. DHCP Reservation

A **DHCP reservation** is useful when a particular device should consistently receive the same IP address.

The DHCP server associates a device's **MAC address** with a specific IP.

Example:

```text
MAC Address              Reserved IP
AA:BB:CC:11:22:33   →    192.168.10.10
```

Whenever that device requests an address, the DHCP server gives it:

```text
192.168.10.10
```

This is particularly useful for:

* Servers
* Printers
* Network devices
* CCTV systems
* IoT devices
* Monitoring systems

---

# 7. Dynamic vs Reserved IP

### Dynamic DHCP

```text
Device → DHCP
          ↓
     Available pool
          ↓
     192.168.10.105
```

The device receives an available address from the pool.

### DHCP Reservation

```text
MAC Address
     ↓
DHCP Server
     ↓
Fixed reservation
     ↓
192.168.10.10
```

The device gets the same address based on its MAC address.

---

# 8. DHCP Server

A **DHCP server** manages IP address allocation.

For example, in your internship lab, you worked with a Linux DHCP server and later with **Kea DHCP**.

A simplified setup is:

```text
                DHCP Server
              192.168.10.1
                    |
             Network Switch
              /     |      \
             /      |       \
        Laptop    Printer   IoT
```

The DHCP server manages the available addresses and provides configuration to clients.

---

# 9. What happens when there are multiple DHCP servers?

Suppose two DHCP servers respond:

```text
             Switch
           /         \
      DHCP Server 1  DHCP Server 2
          |              |
       Offer A         Offer B
```

The client may receive multiple offers and select one.

In a properly managed organizational network, DHCP servers are configured deliberately, often with redundancy or clearly separated scopes, to avoid conflicting assignments.

---

# 10. DHCP Relay

A DHCP Discover is initially broadcast, and routers normally don't forward broadcasts between subnets.

Suppose:

```text
Subnet A                         Subnet B

Laptop                          DHCP Server
192.168.10.x                     192.168.20.10
    |                                 |
    +------ Router / L3 Switch -------+
```

The DHCP server is on another subnet.

A **DHCP Relay Agent** forwards DHCP requests between the client network and DHCP server.

```text
Client
  |
  | Broadcast
  ↓
DHCP Relay
  |
  | Forwarded request
  ↓
DHCP Server
```

This allows one centralized DHCP server to serve multiple networks.

---

# 11. DHCP and DNS

DHCP and DNS perform different jobs:

```text
DHCP
 ↓
"Which IP address should this device use?"

DNS
 ↓
"What IP address belongs to this hostname?"
```

Example:

```text
DHCP:
Laptop → 192.168.10.105

DNS:
server.example.com → 192.168.10.105
```

When DHCP and DNS are integrated, device provisioning can become much more automated.

---

# 12. DHCP in your internship project

Your work with **Kea DHCP + Python + DNS** goes one step beyond basic DHCP.

A simplified version of your intended workflow is:

```text
        Administrator
              |
              ↓
        Google Sheet
              |
              ↓
        Python Script
              |
       ┌──────┴──────┐
       ↓             ↓
   Kea DHCP         DNS
       ↓             ↓
 DHCP Reservation  Hostname
       └──────┬──────┘
              ↓
       Network Device
```

Instead of manually configuring every device, an administrator can enter device information once, and automation can update DHCP reservation and DNS-related configuration.

That turns DHCP from simply **"giving out IP addresses"** into part of **automated network provisioning**.
