# Build-and-Configure-a-Firewall
</p> Building and configuring a firewall is crucial for protecting networks from unauthroized access and potential threats. In this project, I will set up and configure an uncomplicated firewall on my Ubuntu VM </p>
h2>Utilities Used</h2>
</p>- Ubuntu </p>
</p>- UFW </p>
</p>- UTM VM setup </p>
<h2>Step-by-Step Walkthrough</h2>
</p> I open my Ubuntu terminal and ensure all packages are updated </p>
<img width="1028" alt="Screenshot 2024-07-08 at 1 55 35 PM" src="https://github.com/bpark1223/Build-and-Configure-a-Firewall/assets/77799235/0fea582c-f44a-43d5-b7be-c0b61483cfaa">
</p> I install my uncomplicated firewall and enable it </p>
<img width="1440" alt="Screenshot 2024-07-08 at 1 58 17 PM 1" src="https://github.com/bpark1223/Build-and-Configure-a-Firewall/assets/77799235/a83c464d-24d2-4d02-be27-007e5691d011">
</p> I allow ssh connections to prevent myself from getting locked out of the system 
<img width="795" alt="Screenshot 2024-07-08 at 2 04 39 PM" src="https://github.com/bpark1223/Build-and-Configure-a-Firewall/assets/77799235/023bdced-42ed-4e37-a90f-c2b02991d0c1">
</p> I can configure the firewall to allow or deny specific services or ports based on my needs. UFW blocks all incoming connections except for the ones explicitly allowed. In my "building a home lab' project, I explicitly allowed incoming traffic from my Kali Linux VM, but for this example, I will deny it. </p>
<img width="765" alt="Screenshot 2024-07-08 at 2 13 51 PM" src="https://github.com/bpark1223/Build-and-Configure-a-Firewall/assets/77799235/b4e51a7c-6cef-45b6-8814-f2cb1dab12b0">
</p> I will enable logging to monitor ufw activity </p>
<img width="726" alt="Screenshot 2024-07-08 at 3 03 41 PM" src="https://github.com/bpark1223/Build-and-Configure-a-Firewall/assets/77799235/8a847045-d451-4579-ac35-fede1671c03c">
</p> I will use nmap from my Kali linux machine to test that the firewall denies it </p>
<img width="633" alt="Screenshot 2024-07-08 at 3 07 20 PM" src="https://github.com/bpark1223/Build-and-Configure-a-Firewall/assets/77799235/d9cd2080-392e-4671-90ac-505cb64d8338">
</p> When Nmap states "host seems down" and suggests using -Pn if the host is actually up but blocking ping probes, it indicates that my UFW configuration is likely successful in blocking ICMP echo requests (ping). Here’s what this message means in the context of my firewall setup:

</p> ICMP Blocking:</p>
</p>-UFW, by default, blocks ICMP echo requests (ping) as a security measure. This is a common practice to prevent potential reconnaissance activities from external sources.
</p>Nmap Behavior: </p>
</p> -Nmap uses ICMP echo requests (ping) as one method to determine if a host is reachable before initiating port scanning. If the host doesn't respond to ICMP pings due to firewall settings, Nmap assumes the host is down unless instructed otherwise.</p>
</p>Pn Option:</p>
</p>-The -Pn option in Nmap skips the host discovery phase (including ping probes) and assumes the host is up. It instructs Nmap to proceed directly to port scanning, regardless of whether ICMP ping probes are blocked or not.</p>
