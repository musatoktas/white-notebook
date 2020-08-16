# FreeBSD Kernel Install as a FIREWALL
```
# cd /usr/src/sys/i386/conf
# cp GENERIC KSPF
```
Adding some options to the kernel file. The options are following;
```
options IPFIREWALL                      #Firewall activation
options IPFIREWALL_VERBOSE              #Logging (syslogd)
options IPFIREWALL_VERBOSE_LIMIT=200    #Log limit per rule
options IPFIREWALL_FORWARD              #Transparent Forwarding support (Req. for Transparent Proxy)
options IPFIREWALL_FORWARD_EXTENDED     #Improved Transparent Forwarding Support
options IPFIREWALL_DEFAULT_TO_ACCEPT    #it sets default rules accept
options IPDIVERT                        #req for programs which uses Divet Sockets like NAT's
options DUMMYNET                        #Traffic Shaper. Req for bandwith
options IPSTEALTH                       #Its forbid to change of TTLs those passing through firewall
                                        #and Hides Firewall from traceroute
options TCP_DROP_SYNFIN                 #drops SYN+FIN Packets
options PFIL_HOOKS
options RANDOM_IP_ID
options INET6
device bpf
options         ALTQ
options         ALTQ_CBQ        # Class Based Queuing (CBQ)
options         ALTQ_RED        # Random Early Detection (RED)
options         ALTQ_RIO        # RED In/Out
options         ALTQ_HFSC       # Hierarchical Packet Scheduler (HFSC)
options         ALTQ_PRIQ       # Priority Queuing (PRIQ)
```
After adding these to the kernel file, you may install the kernel like this;
```
# cd /usr/src
# make buildkernel KERNCONF=KSPF
# make installkernel KERNCONF=KSPF
```
