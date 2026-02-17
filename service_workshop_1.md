# Service oncall workshop 1

**Lecture:** https://quip-amazon.com/9ZbWAGZTcTMF/Workshop-1-Understanding-Nitro-and-Getting-Ready-to-Hold-the-Pager
**Workshop sheet:** https://quip-amazon.com/61dLABndsQZM/EC2-Chronos-Oncall-Workshop-Activities

[tags]: # (#service #nitro #card #keg #NX)

> [!TODO] TODO
> add tools to dev desktop
> - https://w.amazon.com/bin/view/Main/AWS/EC2/Security/SubstrateAccessControl/Seatbelt/InstallCLI/#HOption1:DeployingCLItoyourDevDesktopThroughPipeline28Recommended29

# What does a Nitro Droplet look like?
Xen droplets could be sshed onto. This is not true for Nitro. Nitro cards can
only be interacted with via COAP APIs, improving security.

If there is an issue with a droplet deployment look to kegs. EDS, is the keg
deployment tracking service.

Real time applications are deterministic. Rustick maybe moved to the real time cores.

**Teams:**
> [!NOTE] Teams You Should Know
> CarbonOS - Team Wiki https://w.amazon.com/bin/view/EC2/Nitro/Carbon/ CarbonOS
> is the operating system running on the Nitro Card. It is basically a Linux
> distribution owned by the Nitro OS team. Several different applications
> (including all of ours) run under it. It uses a Linux kernel.
> 
> Networking (NX) Application - Wiki
> https://w.amazon.com/bin/view/EC2/NX#Contacting +
> https://w.amazon.com/bin/view/Dongle/EC2-Dongle NX is the application which
> handles Networking for EC2 customers. They are particularly crucial to our
> team, since fundamentally Time Synchronization does require Networking (need
> to ask other clocks what time it is!). Notably, they handle INSTANCE
> networking - the Nitro Card itself might have a Substrate network interface
> where it can reach out to services e.g. DNS/NTP, which do NOT go through NX.

The slow path for NX.

Everything exposed through NX is real time. For example the PHC is real time.

More nitro cards are being added to nitro hosts so that hosts can have more
instances.

`netcfg` can be used to get card types.

> [!QUESTION] Questions
> What ntp info does rustick get from chronyd? - ANSWERED
> - root deploy, root dispersion
>
> Synchronize PHC to System Clock. The System Clock gets disciplined by Chronyd
> to ~15 usec CEB, so Pacemaker synchronizes the PHC to that.
>
> If running a singe card coap command on a droplet with multiple cards will be
> get an error?

```d2
EC2 Chronos Control Plane -> NSYNC: Our control plane sends updates to NSYNC.
NSYNC -> Centurion: Centurion gets info from NSYNC, and maybe only nync
Centurion -> Droplets
```

```d2 rendered

              ┌──────────────────────────┐         
              │EC2 Chronos Control Plane │         
              │                          │         
              └──────────────────────────┘         
                         │                         
     Our control plane sends updates to NSYNC.     
                         │                         
                         ▼                         
                     ┌────────┐                    
                     │ NSYNC  │                    
                     │        │                    
                     └────────┘                    
                         │                         
Centurion gets info from NSYNC, and maybe only nync
                         │                         
                         ▼                         
                   ┌──────────┐                    
                   │Centurion │                    
                   │          │                    
                   └──────────┘                    
                         │                         
                         ▼                         
                    ┌─────────┐                    
                    │Droplets │                    
                    │         │                    
                    └─────────┘                    
```

From gunpowder operator hosts we can make coap calls to nitro droplets.

https://code.amazon.com/packages/GTSAllowlistConfig/blobs/mainline/--/configuration/brazil-config/gts-allowlist-config/operator/gts-operator-ec2-chronos.cfg
`ANY` replace with the card identifier.


Useful COAP manual from carbon team: https://w.amazon.com/index.php/EC2/Nucleus/Carbon/CoapAPIs

Domain IDs are specific to an instance on a droplet. The instance will get a
new domain IDs if moved to a new droplet.

---
# Workshop activities scratchpad
```
coap -y -Z ARN51 coaps+tcp://10.18.233.144/api-v1/debug/ls?-l
coap -Z ARN51 coaps+tcp://10.18.233.144/api-v1/debug/utils/pstime?rustick

# get all the cards on a droplet
coap -Z ${EC2_DATACENTER} coaps+tcp://10.18.233.144/api-v1/host/proxy/cards -Y
```

## Workshop 2
Needed to install `toolbox install ripcli`

```bash
# If a local zone:
titan_local_zone=IAD1
az=$($(ripcli -n ${titan_local_zone} -a parent_dimension_key),,)

# If not a local zone:
az=<INSERT_AZ_LOWERCASE>

# Common
account_email_address="ec2-droplet-logs+${az}@amazon.com"
account_id=$(isengard find-account ${account_email_address})
role=EC2GreenDropletLogsAccess
region_name=$(ripcli -r ${az:0:3} -a region_name)
path="/cloudwatch/home?region=${region_name}#logsV2:logs-insights"
path_encoded=$(python3 -c "import urllib.parse;print(urllib.parse.quote(input()))" <<< "${path}")

echo "https://isengard.amazon.com/federate?account=${account_id}&role=${role}&destination=${path_encoded}"
```
