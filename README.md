# Footprinting-and-Reconnaissance

Reconnaissance refers to collecting information about a target, which is the first step in any attack on a system. It has its roots in military operations, where the term refers to the mission of collecting information about an enemy. Reconnaissance helps attackers narrow down the scope of their efforts and aids in the selection of weapons of attack. Attackers use the gathered information to create a blueprint, or "footprint," of the organization, which helps them select the most effective strategy to compromise the system and network security.

Similarly, the security assessment of a system or network starts with the reconnaissance and footprinting of the target. Ethical hackers and penetration (pen) testers must collect enough information about the target of the evaluation before initiating assessments. Ethical hackers and pen testers should simulate all the steps that an attacker usually follows to obtain a fair idea of the security posture of the target organization. In this scenario, you work as an ethical hacker with a large organization. Your organization is alarmed at the news stories concerning new attack vectors plaguing large organizations around the world. Furthermore, your organization was the target of a major security breach in the past where the personal data of several of its customers were exposed to social networking sites.

Objective
The objective of the lab is to extract information about the target organization that includes, but is not limited to:

Organization Information Employee details, addresses and contact details, partner details, weblinks, web technologies, patents, trademarks, etc.

Network Information Domains, sub-domains, network blocks, network topologies, trusted routers, firewalls, IP addresses of the reachable systems, the Whois record, DNS records, and other related information

System Information Operating systems, web server OSes, location of web servers, user accounts and passwords, etc.

## Overview of Footprinting
Footprinting refers to the process of collecting information about a target network and its environment, which helps in evaluating the security posture of the target organization's IT infrastructure. It also helps to identify the level of risk associated with the organization's publicly accessible information.

Footprinting can be categorized into passive footprinting and active footprinting:

Passive Footprinting: Involves gathering information without direct interaction. This type of footprinting is principally useful when there is a requirement that the information-gathering activities are not to be detected by the target.

Active Footprinting: Involves gathering information with direct interaction. In active footprinting, the target may recognize the ongoing information gathering process, as we overtly interact with the target network.

Lab 1: Perform Footprinting Through Search Engines
Task 1: Gather Information using Advanced Google Hacking Techniques

1. Launch any web browser, and go to https://www.google.com (here, I are using Mozilla Firefox).
2. In the search bar search for intitle:login site:eccouncil.org. This search command uses intitle and site Google advanced operators, which restrict results to pages on the eccouncil.org website that contain the login pages.
3. 1
4. Similarly, type the command EC-Council filetype:pdf ceh in the search bar to search your results based on the file extension and the keyword (here, ceh). Click on any link from the results (here, CEH-brochure.pdf) to view the pdf file. Here, the file type pdf is searched for the target organization EC-Council. The result might differ when you perform this task. The PDF and other documents from a target website may provide sensitive information about the target's products and services. They may help attackers to determine an attack vector to exploit the target.
5. 2
6. The page appears displaying the PDF file, as shown in the screenshot.
7. Apart from the aforementioned advanced Google operators, you can also use the following to perform an advanced search to gather more information about the target organization from publicly available sources. cache: This operator allows you to view cached version of the web page. [cache:www.eccouncil.org]- Query returns the cached version of the website www.eccouncil.org, allinurl: This operator restricts results to pages containing all the query terms specified in the URL. [allinurl: EC-Council career]-Query returns only pages containing the words "EC-Council" and "career" in the URL, inurl: This operator restricts the results to pages containing the word specified in the URL [inurl: copy site:www.eccouncil.org]-Query returns only pages in EC-Council site in which the URL has the word "copy", allintitle: This operator restricts results to pages containing all the query terms specified in the title. [allintitle: detect malware]-Query returns only pages containing the words "detect" and "malware" in the title

Lab 2: Perform Footprinting Through Internet Research Services
Task 1: Find the Company's Domains, Subdomains and Hosts using Netcraft and DNSdumpster

Domains and sub-domains are part of critical network infrastructure for any organization. A company's top-level domains (TLDs) and subdomains can provide much useful information such as organizational history, services and products, and contact information. A public website is designed to show the presence of an organization on the Internet, and is available for free access.

1. Launch any web browser, and go to https://www.netcraft.com (here, we are using Mozilla Firefox).
2. Netcraft page appears, as shown in the screenshot.
3. 4
4. Click on Resources tab and select Research Tools.
5. 5
6. In the Tools | Netcraft page, click on Site Report option.
7. 6
8. The What's that site running? page appears. To extract information associated with the organizational website such as infrastructure, technology used, sub domains, background, network, etc., type the target website's URL (here, https://www.certifiedhacker.com) in the text field, and then click the LOOK UP button, as shown in the screenshot.
9. 7
10. The Site report for https://www.certifiedhacker.com page appears, containing information related to Background, Network, Hosting History, etc., as shown in the screenshot.
11. 8
12. In the Network section, click on the website link (here, certifiedhacker.com) in the Domain field to view the subdomains.
13. 9
14. The result will display the subdomains of the target website along with netblock and operating system information, as shown in the screenshot.
15. 10
16. Now, I will find company's DNS Servers along with Geo IP and domain mapping using DNSdumpster website.
17. Open a new tab in Firefox browser and go to https://dnsdumpster.com/. Search for certifiedhacker.com in the search box.
18. 11
19. The website displays the GEOIP of Host Locations, as shown in the screenshot.
20. 12
21. Scroll down to view the list of DNS Servers, MX Records, Host Record (A) along with their IP addresses.
22. 13
23. Further, scroll down to view the domain mapping of the website.
24. 14
25. Click on Download .xlsx of Hosts button to download the list of hosts.
26. 15
27. Navigate to the Downloads folder and double-click on certifiedhacker.com-xxxxxxx.xlsx file to view the list of Hosts. The Excel sheet displays the details such as Hostname, IP Address, Reverse DNS, Netblock Owner, Country, HTTP /Title, etc.
28. 16
29. This concludes the demonstration of finding the company's domains and subdomains and Hosts using the Netcraft tool and DNSdumpster. The attackers can use this collected list of subdomains to perform web application attacks on the target organization such as injection attacks, brute-force attack, and denial-of-service (DoS) attacks.

Lab 3: Perform Footprinting Through Social Networking Sites
Task 1: Gather Personal Information from Various Social Networking Sites using Sherlock
Sherlock is a python-based tool that is used to gather information about a target person over various social networking sites. Sherlock searches a vast number of social networking sites for a given target user, locates the person, and displays the results along with the complete URL related to the target person.

1. Turn on the Parrot Security virtual machine
2. Open a Terminal window and execute sudo su to run the programs as a root user
3. Run sherlock "Elon Musk" command and you will get all the URLs related to Elon Musk, as shown in the screenshot. Scroll-down to view all the results.
4. 17
5. The attackers can further use the gathered URLs to obtain sensitive information about the target such as DOB, employment status and information about the organization that they are working for, including the business strategy, potential clients, and upcoming project plans.

Lab 4: Perform Whois Footprinting
Task 1: Perform Whois Lookup using DomainTools

1. Open any web browser, and go to https://whois.domaintools.com
2. The Whois Lookup website appears, as shown in the screenshot. Now, in the search bar, search for www.certifiedhacker.com.
3. 18
4. This search result reveals the details associated with the URL entered, www.certifiedhacker.com, which includes organizational details such as registration details, name servers, IP address, location, etc., as shown in the screenshots.
5. 19
6. 20

Lab 5: Perform DNS Footprinting - DNS considered the intermediary source for any Internet communication. The primary function of DNS is to translate a domain name to IP address and vice-versa to enable human-machine-network-internet communications. Since each device has a unique IP address, it is hard for human beings to memorize all IP addresses of the required application. DNS helps in converting the IP address to a more easily understandable domain format, which eases the burden on human beings.
Task 1: Gather DNS Information using nslookup Command Line Utility and Online Tool - nslookup is a network administration command-line utility, generally used for querying the DNS to obtain a domain name or IP address mapping or for any other specific DNS record. This utility is available both as a command-line utility and web application.

1. Launch a Command Prompt, and run nslookup command. This displays the default server and its address assigned to the Windows 11 machine.
2. In the nslookup interactive mode, type set type=a and press Enter. Setting the type as "a" configures nslookup to query for the IP address of a given domain.
3. Type the target domain www.certifiedhacker.com and press Enter. This resolves the IP address and displays the result, as shown in the screenshot.
4. 21
5. The first two lines in the result are:
Server: dns.google and Address: 8.8.8.8
This specifies that the result was directed to the default server hosted on the local machine (Windows 11) that resolves your requested domain.
6. Thus, if the response is coming from your local machine's server (Google), but not the server that legitimately hosts the domain www.certifiedhacker.com; it is considered to be a non-authoritative answer. Here, the IP address of the target domain www.certifiedhacker.com is 162.241.216.11.
7. Since the result returned is non-authoritative, you need to obtain the domain's authoritative name server.
8. Type set type=cname and press Enter. The CNAME lookup is done directly against the domain's authoritative name server and lists the CNAME records for a domain.
9. This returns the domain's authoritative name server (ns1.bluehost.com), along with the mail server address (dnsadmin.box5331.bluehost.com), as shown in the screenshot.
10. 22
11. Since I have obtained the authoritative name server, you will need to determine the IP address of the name server. Issue the command set type=a and press Enter. Type ns1.bluehost.com (or the primary name server that is displayed in your lab environment) and press Enter. This returns the IP address of the server, as shown in the screenshot.
12. 23
13. The authoritative name server stores the records associated with the domain. So, if an attacker can determine the authoritative name server (primary name server) and obtain its associated IP address, he/she might attempt to exploit the server to perform attacks such as DoS, DDoS, URL Redirection, etc.
14. Now, I will use an online tool NSLOOKUP to gather DNS information about the target domain. Open any web browser and go to http://www.kloth.net/services/nslookup.php (here, we are using Mozilla Firefox).
15. Once the site opens, in the Domain: field, enter www.certifiedhacker.com. Set the Query: field to default [A (IPv4 address)] and click the Look it up button to review the results that are displayed.
16. 24
17. In the Query: field, click the drop-down arrow and check the different options that are available, as shown in the screenshot. As I can see, there is an option for AAAA (IPv6 address); select that and click Look it up. Perform queries related to this, since there are attacks that are possible over IPv6 networks as well.
18. 25
19. 26

Lab 6: Perform Network Footprinting - With the IP address, hostname, and domain obtained in the previous information gathering steps, as a professional ethical hacker, your next task is to perform network footprinting to gather the network-related information of a target organization such as network range, traceroute, TTL values, etc. This information will help you to create a map of the target network and perform a man-in-the-middle attack.

Task 1: Perform Network Tracerouting in Windows and Linux Machines - The route is the path that the network packet traverses between the source and destination. Network tracerouting is a process of identifying the path and hosts lying between the source and destination. Network tracerouting provides critical information such as the IP address of the hosts lying between the source and destination, which enables you to map the network topology of the organization. Traceroute can be used to extract information about network topology, trusted routers, firewall locations, etc. 

1. In the Windows 11 machine, open the Command Prompt window. Run tracert www.certifiedhacker.com command to view the hops that the packets made before reaching the destination.
2. 27
3. Run tracert /? command to view the different options for the command, as shown in the screenshot.
4. 28
5. Run tracert -h 5 www.certifiedhacker.com command to perform the trace, but with only 5 maximum hops allowed.
6. 29
7. Switch to the Parrot Security machine and open a Terminal window. Run traceroute www.certifiedhacker.com command to view the hops that the packets made before reaching the destination.
8. 30

Lab 7: Perform Footprinting using Various Footprinting Tools
Task 1: Footprinting a Target using Recon-ng

1. In the Parrot Security machine, open a Terminal window and execute sudo su to run the programs as a root user .
2. Now, run cd command to jump to the root directory and run recon-ng command to launch the application.
3. 31
4. Run help command to view all the commands that allow you to add/delete records to a database, query a database, etc.
5. 32
6. Run marketplace install all command to install all the modules available in recon-ng.
7. 33
8. After the installation of modules, run modules search command. This displays all the modules available in recon-ng.
9. 34
10. Run workspaces command to view the commands related to the workspaces.
11. 35
12. Create a workspace in which to perform network reconnaissance. In this task, we shall be creating a workspace named CEH. To create the workspace, run workspaces create CEH command. This creates a workspace named CEH.
13. 36
14. Enter workspaces list. This displays a list of workspaces (along with the workspace added in the previous step) that are present within the workspaces databases.
15. 37
16. Issue the command db insert domains. Under domain (TEXT) option type certifiedhacker.com and press Enter. In the notes (TEXT) option press Enter. This adds certifiedhacker.com to the present workspace. I can view the added domain by issuing the show domains command, as shown in the screenshot.
17. 38
18. Harvest the hosts-related information associated with certifiedhacker.com by loading network reconnaissance modules such as brute_hosts, Netcraft, and Bing.
19. Issue modules load brute command to view all the modules related to brute forcing. In this task, we will be using the recon/domains-hosts/brute_hosts module to harvest hosts.
20. 39
21. To load the recon/domains-hosts/brute_hosts module, issue modules load recon/domains-hosts/brute_hosts command. Issue run command. This begins to harvest the hosts, as shown in the screenshot.
22. 40
23. I have now harvested the hosts related to certifiedhacker.com using the brute_hosts module. You can use other modules such as Netcraft and Bing to harvest more hosts.
24. Now, perform a reverse lookup for each IP address (the IP address that is obtained during the reconnaissance process) to resolve to respective hostnames.
25. Execute modules load reverse_resolve command to view all the modules associated with the reverse_resolve keyword. In this task, we will be using the recon/hosts-hosts/reverse_resolve module.
26. Run the modules load recon/hosts-hosts/reverse_resolve command to load the module.
27. Issue the run command to begin the reverse lookup.
28. 41
29. Once done with the reverse lookup process, run the show hosts command. This displays all the hosts that are harvested so far, as shown in the screenshot.
30. 42
31. Execute modules load reporting command to view all the modules associated with the reporting keyword. In this lab, we will save the report in HTML format. So, the module used is reporting/html.
32. Run the modules load reporting/html command.
33. Observe that you need to assign values for CREATOR and CUSTOMER options while the FILENAME value is already set, and you may change the value if required. To do so, run the below commands:
    options set FILENAME /home/attacker/Desktop/results.html. By issuing this command, you are setting the report       name as results.html and the path to store the file as Desktop.
    options set CREATOR [your name] (here, Jason).
    options set CUSTOMER Certifiedhacker Networks (since you have performed network reconnaissance on                   certifiedhacker.com domain).
34. Use the run command and press Enter to create a report for all the hosts that have been harvested.
35. 43
36. The generated report is saved to /home/attacker/Desktop/.
37. Navigate to /home/attacker/Desktop/, right-click on the results.html file, click on Open With, and select the Firefox ESR Web Browser browser from the available options.
38. 44
39. The generated report appears in the Firefox browser, displaying the summary of the harvested hosts. I can expand the Hosts node to view all the harvested hosts, as shown in the screenshot.
40. 45
41. Now, I will use Recon-ng to gather personnel information. Open a Terminal window and execute sudo su to run the programs as a root user
42. Run cd command to jump to the root directory and run recon-ng command.
43. Add a workspace by issuing the command workspaces create reconnaissance and press Enter. This creates a workspace named reconnaissance.
44. 46
45. Set a domain and perform footprinting on it to extract contacts available in the domain.
46. Execute modules load recon/domains-contacts/whois_pocs command. This module uses the ARIN Whois RWS to harvest POC data from Whois queries for the given domain.
47. Run the info command command to view the options required to run this module.
48. Run options set SOURCE facebook.com command to add facebook.com as a target domain.
49. 47
50. Execute the run command. The recon/domains-contacts/whois_pocs module extracts the contacts associated with the domain and displays them, as shown in the screenshot
51. 48
52. Until now, I have obtained contacts related to the domains. Note down these contacts' names. Now, I will use Recon-ng to extract a list of subdomains and IP addresses associated with the target URL.
53. Now, run cd command to jump to the root directory and run recon-ng command.
54. To extract a list of subdomains and IP addresses associated with the target URL, we need to load the recon/domains-hosts/hackertarget module.
55. Run the modules load recon/domains-hosts/hackertarget command and run options set SOURCE certifiedhacker.com command.
56. Execute the run command. The recon/domains-hosts/hackertarget module searches for list of subdomains and IP addresses associated with the target URL and returns the list of subdomains and their IP addresses.
57. 49


