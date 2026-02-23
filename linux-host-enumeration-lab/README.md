### Linux Host Enumeration and Log Investigation

#### Lab Overview

Simulated internal system access to a Linux host to perform basic enumeration and identify system information relevant to security monitoring and incident response.

---

#### Environment

* Attacker Machine: Kali Linux
* Target Machine: Ubuntu Desktop VM
* Virtualization Platform: VMware Workstation
* Network Type: Host-Only Internal Lab Network

---

#### Objective

Perform local host enumeration using Linux CLI utilities to gather system information, identify user accounts, review log files, and detect potentially suspicious activity.

---

#### Enumeration Activities

Checked current logged-in user:

```
whoami
```

Identified system hostname:

```
hostname
```

Reviewed current working directory:

```
pwd
```

Listed directory contents and hidden files:

```
ls -la
```

---

#### User Enumeration

Displayed local user accounts:

```
cat /etc/passwd
```

Identified privileged users and service accounts present on the system.

---

#### Process Review

Listed active processes:

```
ps aux
```

Used to identify unusual or unauthorized running services.

---

#### Network Connections

Checked listening ports and active connections:

```
ss -tuln
```

Reviewed for unknown services exposed on the host.

---

#### Log File Investigation

Navigated to system logs directory:

```
cd /var/log
```

Reviewed authentication logs for login activity:

```
cat auth.log
```

Used for identifying failed login attempts or unauthorized access attempts.

---

#### Security Relevance

These commands are commonly used during post-compromise investigations to assess system state, user presence, and potential indicators of compromise.

---

#### Mitigation Considerations

* Monitor authentication logs regularly
* Restrict unnecessary services
* Implement least privilege access
* Audit user accounts periodically
