# Ezmeral-FIrewall-Rules
Creating Firewalld services and the Firewalld interface that includes the rules. 

When using HPE Ezmeral, you either have to either preconfigure the firewalls or turn them off. 
If your cluster is in its own segmented subnet with no internet access, you can run with no firewall per system. 
Being paranoid, I tend to want a firewall up and running at all times.  (Especially if you're planning on building a hybrid cluster) 

For my home cluster I use webmin and FirewallD as my firewall. 

I've created this repositiory to have a set of additional rules that are not standard and a firewall interface containing these and the standard rules. 

Also included are rules for MapR too. 

Note: These are the default values.  If you want to change the ports used, you will need to update these files. 

According to the Firewalld documentation, these files have the following template: 
Note that not all fields are required.

<?xml version="1.0" encoding="utf-8"?>
<service>
  <short>My Service</short>
  <description>description</description>
  <port port="137" protocol="tcp"/>
  <protocol value="igmp"/>
  <module name="nf_conntrack_netbios_ns"/>
  <destination ipv4="224.0.0.251" ipv6="ff02::fb"/>
  <include service="ssdp"/>
  <helper name="ftp"/>
</service>
