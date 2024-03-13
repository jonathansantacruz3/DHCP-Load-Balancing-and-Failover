![DHCP Load Balancing and Failover](https://github.com/jonathansantacruz3/DHCP-Load-Balancing-and-Failover/assets/151465848/bb187560-3750-4122-b0b9-11860ec0a96a)


<h1>DHCP Load Balancing and Failover</h1>
This tutorial outlines the implementation of a failover configuration and load balancing between two DHCP servers. Load balancing helps distribute the loads of incoming queries between both servers and increases performance. In a failover configuration, the set primary server will handle all queries, and the secondary server will replace the primary in the event that it fails.   <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Hyper-V (Virtual Machines/Compute)
  
<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 11 Pro (23H2)

<h2>Configuration Steps</h2>

The infrastructure set here is based on two servers running Windows Serer 2022 with the DHCP role installed on them. The client PC, StarLord, is running Windows 11 Pro and receives its data from DHCP 1. DHCP 1 has an address pool named ProjectLAN and has a range from 192.168.0.25 through 192.168.0.50. 
