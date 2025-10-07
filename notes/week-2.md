# week 2

### red team: packet interception

- packet sniffing
  - broadcast media (shared ethernet, wireless)
  - promiscuous network interface reads/records all packets (including passwords if not encrypted!) passing by

### red team: fake identity

- ip spoofing: injection of packet with false source addr

### mac addrs

- 32 bit ip addr
  - network layer addr for interface
  - used for layer 3 forwarding
- mac (lan or physical or ethernet) addr
  - used locally to get frame from one interface to another physically connected interface (same subnet)
  - 48-bit mac addr for most lans burned in nic rom, also sometimes settable in software
- each interface on lan has unique 48-bit mac addr & locally unique 32-bit ip addr
- addr allocation administered by ieee
- manufacturer buys portion of mac addr space to assure uniqueness
- mac flat addr: portability
  - can move interface from one lan to another
  - ip addr is not portable

### arp: addr resolution protocol

- arp table: each ip node (host, router) on lan has table
- ip/mac mappings for some lan nodes: (ip, mac, ttl)

### tcpdump

- wireshark but better bc it is a cli
- commands (usually run with root)
  - list interfaces: `tcpdump -D`
  - basic capture on specific interface: `tcpdump -i <interface>`
  - capture & save to file: `tcpdump -i <interface> -w <pcap file>`
  - adding filters: tcpdump uses same berkeley packet filter (bpf) syntax as wireshark's capture filters
    - host: `tcpdump -i <interface> host <host ip>`
    - port: `tcpdump -i <interface> port <port num>`
    - more complex: `tcpdump -i eth0 src <src ip> and dst port <dst port num>`
