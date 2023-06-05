## Chapter 1 - Mastering Security Basics

CIA => Confidentiality, Integrity, Availability

### Confidentiality

* Makes sure that authorized users can access target ressources and unauthorized users can not.
* The best way to protect the confidentiality of data is by encrypting it.
* PPI = Personally Identifiable Information (medical information, credit card data).

#### Access Controls

* Identification => Unique username
* Authentication => Password
* Authorization => Permissions

### Integrity

* Integrity provides assurances that data has not changed. This includes ensuring that no one has modified the data.
* A hashing algorithm creates a fixed-length, irreversible output. If the data never changes, the resulting hash will always be the same.
    * By comparing hashes created at 2 different times, you can determine if the original data is still the same. If the hashes are the same, the data is the same. If the hashes are different, the data has changed.

### Availability

* Availability ensures that systems are up and operational when needed and often addresses single points of failure.

#### Redundancy and Fault Tolerance

* **Redundancy** adds duplication to critical systems and provides **fault tolerance**.
* If a critical component has a fault, the redundancy's duplication allows the service to continue without interruption.
* A common goal of **fault tolerance** and **redundancy** techniques is to remove each ***single point of failure*** (***SPOF***).
    * Example : if a server has a single drive, the drive is an ***SPOF*** because its failure takes down the server.

Redundancy examples :
* Disk redundancies => RAID-1 (mirroring), RAID-5 (striping with parity) or RAID-10 (striping with a mirror)
* Server redundancies => Virtualization
* Network redundancies => Load balancing, multiple Network Interface Cards (NICs)
* Power redundancies => Uninterruptible power supplies (UPS)

#### Scalability and Elasticity

* ***Scalability*** refers to **manually** adding or removing resources to a system to scale up or out.
* ***Elasticity*** refers to **dynamically** adding or removing resources to a system to scale it.
* "Scale up" = Add more ressources.
* "Scale out" = Add more servers.

#### Resiliency

***Resiliency*** methods help systems heal themselves or recover from faults with minimal downtime.

---

### Basic Risk Concept

If a company decides to encrypt all data, it will need approximately 40% more disk space to store it. Additionally, when processing the data, it consumes more memory and processing power to encrypt it and decrypt the date, effectively slowing down applications.

* ***Risk*** is the possibility or likelihood of a threat exploiting a vulnerability resulting in a loss.
* A ***threat*** is any circumstance or event that has the potential to compromise confidentiality, integrity or availability.
* A ***vulnerability*** is a weakness.
* A ***security incident*** is an adverse event or series of events that can negatively affect the confidentiality, integrity or availability of an organization's information technology (IT) systems and data.
* ***Risk mitigation*** (=reducing risks) reduces the chances that a threat will exploit a vulnerability.
    * You reduce risks by implementing controls (countermeasures or safeguards).

### Security Controls

* **Managerial controls**
  * Managerial controls are primarily administrative in function and are typically documented in an organization's written security policy.
  * They use planning and assessment methods to provide an ongoing review of the organization's ability to reduce and manage risk.
  * Examples :
    * **Risk assessments** => Categorize risks based on probability and impact.
    * **Vulnerability assessments** => Discover current vulnerabilities.
* **Operational controls**
  * Helps to ensure the day-to-day operations of an organization comply with their overall security plan.
  * **Awareness and training**
  * **Configuration management** => Ensure that systems start in a secure, hardened state.
  * **Media protection**
  * **Physical and environmental protection** => Cameras, door locks,...
* **Technical controls**
  * Technical controls use technology such as hardware, software and firmware to reduce vulnerabilities.
  * **Encryption**
  * **Anti-virus software**
  * **Intrusion detection systems** (IDS) and **intrusion prevention systems** (IPS)
  * **Firewall**
  * **Least privilege**

**Control types :**

* **Preventive controls** => Hardening, Training, Security guards, Change management, Account disablement policy, IPS.
* **Detective controls** => Log monitoring, security and event management (SIEM) systems, Security audits, video surveillance, motion detection, IDS.
* **Corrective controls** => Backups and system recovery, incident handling processes (incident response plan).
* **Deterrent controls** (=Attempt to discourage threats) => Cable locks, Physical locks.
* **Compensating controls** (=Alternative controls used instead) => Smart cards.
* **Physical controls**

---

### Useful Commands

* `hping` => Can send the pings using TCP, UDP and ICMP (Linux only).
* `ifconfig` (Linux) or `ipconfig` (Windows) => Display IP information.

  * `ipconfig /all`, `ipconfig /displaydns`, `ipconfig /flushdns`.
* `netstat` => Displays a listing of all open TCP connections.
  * `netstat -a` => All TCP connections + UDP
  * `netstat -r` => Routing table
  * `netstat -p tcp` => Display statistics on specific protocol (in this case "tcp").
* `tracert` (Windows) or `traceroute` (Linux) => Display path to destination
* `pathping` => Combines "ping" and "tracert" command.
* `arp -a` => Displays the arp cache (Windows).

---

### Windows Logs

* **Security log**
  * The security log functions as a security log, an audit log and an access log.
* **System log**
  * Records event related to the functioning of the OS. This can include when it starts, shut down, information on services starting and stopping, drivers loading or failing,...
* **Application log**
  * Records events sent to it by applications or programs running on the system.

### Centralized Logging Methods

* SIEM Systems => Provides a central solutions for collecting, analyzing and managing data from multiple sources.
* Syslog
* Syslog-ng and rsyslog
* NXLog => Like Syslog but compatible with BOTH Linux and Windows.
