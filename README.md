# CCNA Full Practice

My Packet Tracer file for the **CCNA Mega Lab** from Jeremy's IT Lab. It's one big topology that covers pretty much every config topic on the CCNA exam, from basic device setup all the way to OSPF, NAT, Layer 2 security, IPv6 and wireless.

The lab was made by Jeremy McDowell (Jeremy's IT Lab), so credit for the lab itself goes to him. If you're studying for the CCNA and haven't seen his free course on YouTube yet, go check it out.

## File

`CCNA_Mega_Lab_Jeremys_IT_Lab11_fixed.pka` - saved in Packet Tracer 9.0, so you'll need 9.0 or newer to open it.

My configs are already in the file. If you want to do it from scratch, open the instructions window and hit **Reset Activity**.

## Topology

- **Edge:** R1 (2911) with two internet links, one to ISP A and one to ISP B
- **Core:** CSW1 and CSW2 (3650), Layer 3 EtherChannel between them
- **Office A:** DSW-A1 / DSW-A2 (distribution), ASW-A1 to ASW-A3 (access), WLC1, LWAP1, PC1, PC2, two IP phones
- **Office B:** DSW-B1 / DSW-B2 (distribution), ASW-B1 to ASW-B3 (access), LWAP2, PC3, an IP phone and SRV1
- Two wireless laptops

## What's covered

| Part | Topics |
|------|--------|
| 1 | Hostnames, enable secret, local user accounts, console line |
| 2 | VLANs, VTPv2, trunking (DTP off, native VLAN), L2 EtherChannel with PAgP and LACP |
| 3 | IP addressing, L3 EtherChannel, HSRPv2 |
| 4 | Rapid PVST+, root bridge placement, PortFast, BPDU Guard |
| 5 | Single-area OSPF, floating static default routes, default route into OSPF |
| 6 | DHCP + relay, DNS, NTP with auth, SNMP, Syslog, IOS upgrade over FTP, SSH, static NAT, PAT, LLDP instead of CDP |
| 7 | Extended ACL, port security, DHCP snooping, DAI |
| 8 | IPv6 addressing (incl. EUI-64), IPv6 static routes |
| 9 | WLC GUI, dynamic interface, WPA2-PSK WLAN |

## Things to keep in mind

- Run `copy running-config startup-config` on every device before you click Check Results. Unsaved configs get zero points.
- Packet Tracer gets slow and buggy with a topology this big. If something starts acting strange, save all the configs, save the file, then close and reopen it.
- NTP takes ages to sync in PT. Configure it and move on, don't wait for it.
- Wireless clients won't get an address from the Wi-Fi DHCP pool. That's a Packet Tracer limitation, not a config mistake.
- For the internet failover test in part 6, you have to remove and re-add `default-information originate` under OSPF, because PT doesn't support the `always` keyword.
