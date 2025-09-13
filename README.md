## Ransomware Recovery
## What Did I Do

I first reviewed the Nmap output in Assignment 1. The scan revealed a list of active devices on the network, including IP addresses such as:

- 192.168.4.1  
- 192.168.4.20  
- 192.168.4.21  
- 192.168.4.22  
- 192.168.4.26  
- 192.168.4.27  
- 192.168.4.34  
- localhost  

Based on the infrastructure and IP mappings, I categorized these devices as domain controllers, file servers, email servers, database servers, web servers, routers, and administrative workstations. This helped me create an initial inventory of critical network assets.

Next, I prioritized the assets by their role in daily operations and recovery importance. Authentication servers, file servers, and communication servers were considered top priorities for recovery after a ransomware attack.

Then, I used outputs from Assignment 3 (including Shields Up and Nessus reports) to identify vulnerabilities requiring patching. I focused on critical threats such as Intel AMT vulnerabilities and insecure SMB configurations, notably on the domain controller at 192.168.4.20.

Combining data from Assignments 1 and 3, I compiled a list of system roles requiring password backups to ensure smooth restoration. This included administrative credentials for domain controllers, servers, and network devices.

Throughout the process, I emphasized practicality and followed best practices in ransomware recovery preparation.

---

## What Are the Results

The analysis led to the development of:

- A prioritized system recovery list  
- A structured backup plan  
- A list of essential passwords to store offline  
- A report on systems needing urgent updates  
- A finalized network device inventory  

**System Recovery Priority:**

1. **Domain Controller (192.168.4.20)** – Manages network-wide authentication and must be restored first.
2. **File Server (192.168.4.22)** – Holds operational documents critical to business continuity.
3. **Email Server (192.168.4.21)** – Required for both internal and external communications.
4. **Database Server (192.168.4.26)** – Supports business and client data.
5. **Web Server (192.168.4.27)** – Ensures continuity of customer-facing functions.
6. **Administrative Workstation (192.168.4.34)** – Needed for managing the recovery process.
7. **Router/Firewall (192.168.4.1)** – Assumed active unless compromised.

**Backup Plan Overview:**

- Active Directory data (domain controller)
- File system snapshots
- Email database backups
- SQL database backups
- Web server content
- Network device configurations
- Offline backups of passwords for key roles:
  - Domain Administrator  
  - File Server Admin  
  - Email Server Admin  
  - Database Admin  
  - Web Server Admin  
  - Router/Firewall Admin  

Offline password storage is critical in case authentication services are compromised.

**Vulnerability Findings:**

- The Domain Controller had several high-risk Intel AMT vulnerabilities:
  - CVE-2020-8752  
  - CVE-2020-8747  
  - CVE-2020-8749  
- Insecure SMB configuration allowed potential man-in-the-middle attacks.
- An untrusted SSL certificate was discovered, posing phishing or impersonation risks.

**Network Inventory:**

All detected IP addresses were assigned roles, including:

- Router/firewall  
- Domain controller  
- File server  
- Email server  
- Database server  
- Web server  
- Admin workstation  
- Localhost (monitoring)

Maintaining a comprehensive inventory supports both proactive security and effective recovery.

**Identified Deficiencies:**

- Nmap did not detect all workstations or IoT devices.
- Vulnerability management is reactive; many critical issues were unaddressed.
- No centralized password vault or formal offline backup procedures for credentials.

**Recommendations:**

- Perform a full asset discovery scan
- Implement a monthly patching and vulnerability cycle
- Establish a secure password vault with offline storage and MFA

These actions would strengthen the business’s ability to recover from ransomware attacks.

---

## What Did I Learn

This assignment taught me that effective ransomware recovery requires:

- **Thorough planning and accurate network visibility:** A full, updated inventory ensures no critical device is overlooked.
- **Asset prioritization:** Restoring services like authentication and file storage first speeds up overall recovery.
- **Regular patching:** Vulnerabilities like those in Intel AMT firmware highlight the need for prompt updates. Insecure configurations (e.g., SMB) are common risks that should not be ignored.
- **Password management:** Even with backups, inaccessible credentials can stall recovery. Offline backups of admin passwords are essential.

Ultimately, ransomware recovery is not just about defense—it’s about resilience. A solid recovery plan enables faster service restoration, reduced downtime, retained customer trust, and stronger long-term cybersecurity practices.
