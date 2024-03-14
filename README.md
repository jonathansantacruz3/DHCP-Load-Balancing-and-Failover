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

<h3>Setting Up Failover on Primary Server</h3>
DHCP 2 also has the role of a DHCP server with a static IP address. It has no specific scope assigned to it because it will serve as a failover to DHCP 1. To configure the failover onto DHCP 2 I need to head over to the primary server's DHCP tab in Server Manager's "Tools" and select "DHCP". This brings up the DHCP snap-in and on the left side panel I'll click on the server's name and then right-click the IPv4 option to disclose the menu where "Configure Failover..." resides. Choosing this option will open up the configuration wizard. 

![image](https://github.com/jonathansantacruz3/DHCP-Load-Balancing-and-Failover/assets/151465848/9f23b309-1947-46c2-9bf1-fd556863c0cb)


<h3>Wizard Configuration</h3>
In the wizard, I will click "Next", and name the partner server's IP and click on "Add server" to add the hostname that will take over if the primary server fails. After confirming the IP and hostname, I will click on next and proceed to the next window. Here in the "Mode" section, I will choose the "Hot Standby" option from the drop down menu. This means the added server will act as the primary if the primary fails to answer queries. I can also choose to set it up as a load balancer where the servers will share the load of queries allowing the system to be optimized. I can change the amount of loads one server can take over the other or have them share evenly. I can also choose to authenticate the failover relationship by requiring a shared secret passcode. 

![image](https://github.com/jonathansantacruz3/DHCP-Load-Balancing-and-Failover/assets/151465848/e5a5de65-f94d-493a-8ebb-7e1deacf28f2)


![image](https://github.com/jonathansantacruz3/DHCP-Load-Balancing-and-Failover/assets/151465848/ae307870-382c-4394-8073-d8f00ea800a8)


![image](https://github.com/jonathansantacruz3/DHCP-Load-Balancing-and-Failover/assets/151465848/027593a7-becf-46b6-a471-bf9803535ef6)

![image](https://github.com/jonathansantacruz3/DHCP-Load-Balancing-and-Failover/assets/151465848/951438e7-75b6-4a39-bb9b-9e9257643314)

![image](https://github.com/jonathansantacruz3/DHCP-Load-Balancing-and-Failover/assets/151465848/31a18b0a-232e-44cc-baf4-6d0924e2ded8)

I can right-click the scope 

