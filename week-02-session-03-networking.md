# Week 2 Session 3 — Networking and DNS

**Status:** Reported complete; original output files not retained.

## Recorded observations

- VM address `10.0.2.15/24` on `enp0s3`; gateway `10.0.2.2`.
- `ip route get 1.1.1.1` selected the default gateway.
- Practiced recognizing local-subnet versus external destinations and possible DNS failures.
- Final checkpoint answers reported: B and C. Original questions are not bundled.

## Interpretation

For the recorded `/24`, `10.0.2.50` is on the same IP subnet. Route selection normally uses the connected route rather than the default route; reachability still depends on the network and destination. A VirtualBox NAT network does not guarantee another machine exists at that address.

Loopback is local to the system. The VM reaches its virtual network through `enp0s3`, not through `lo`. NAT translates guest traffic through the host's networking.

## Repeatable diagnostic sequence

```bash
ip -br address
ip route
ip route get 1.1.1.1
ping -c 4 10.0.2.2
ping -c 4 1.1.1.1
getent hosts ubuntu.com
resolvectl status
```

Compare address, route, reachability, and name lookup separately. Failed ping alone does not prove a network outage because ICMP may be filtered. `getent hosts` tests system name resolution; it can include sources other than DNS.

**IT connection:** distinguishing local configuration, routing, and name-resolution problems.
