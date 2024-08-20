# sysevent_int
sysevent attack generator - No external exposure via load balancer

Introduction This container will fill your (demo) environment with random events for showcasing purposes. It will (by default, configurable) randomly spawn events pausing between 1800 and 7200 seconds. Also an interactive menu is available to spawn a specific event. Currently 21 different events will be run (see screenshot below).

Events are based on the default Sysdig managed policies (all Managed policies enabled)

Current events Currently the following event generation scripts are available: Modify binary dirs Remove Bulk Data from Disk Modify ld.so.preload Read Shell Configuration File Detect crypto miners using the Stratum protocol Reconnaissance attempt to find SUID binaries Kill known malicious process Tampering with Security Software in Container Base64-encoded Python Script Execution Dump memory for credentials Read sensitive file untrusted Netcat Remote Code Execution in Container Contact EC2 Instance Metadata Service From Container Delete or rename shell history Create Symlink Over Sensitive Files Search Private Keys or Passwords Code compiler downloaded and launched in container Malicious IPs or domains detected on command line Create Hardlink Over Sensitive Files Diamorphine Rootkit Activity Execute Eicar malware

Configuration and Deployment: Create the following deployment. Make sure the namespace sysevent exists. The environment variables minsleep and maxsleep can be omitted. They will default to 1800 and 7200 seconds respectively. In case you want to use the generator only in manual mode use the environment variable pauseonstart value true to disable automatic event generation (default false)

Create kubernetes namespace called sysevent 
kubectl apply -n sysevent -f <filename.yaml>
