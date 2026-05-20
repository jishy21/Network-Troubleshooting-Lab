# Network Troubleshooting Lab

## Objective
Built a virtualized Windows network troubleshooting lab using VirtualBox, Windows Server, and Windows 10 to practice diagnosing and resolving real-world help desk and connectivity issues.

This lab focused on DNS troubleshooting, DHCP failures, APIPA addressing, and network diagnostic tools commonly used in enterprise IT support environments.

---

# Environment

- Windows Server 2019/2022
- Windows 10 Client
- Oracle VirtualBox
- Internal Network + NAT configuration

---

# Skills Demonstrated

- DNS troubleshooting
- DHCP troubleshooting
- APIPA diagnosis
- Connectivity testing
- Network recovery
- Windows command-line troubleshooting
- Tier 1 / Tier 2 support workflow

---

# Tools Used

- PowerShell
- ipconfig
- ping
- nslookup
- tracert
- Windows Network Settings
- VirtualBox networking

---

# Scenario 1 — Baseline Connectivity

Verified successful communication between the client VM, domain controller, and internet connectivity using ping tests and IP configuration checks.

### Commands Used

```powershell
ipconfig /all
ping google.com
ping 8.8.8.8
```

---

# Scenario 2 — DNS Failure Simulation

Configured an invalid DNS server to intentionally break DNS resolution while maintaining internet connectivity.

### Result

- DNS name resolution failed
- Internet connectivity still functioned via direct IP communication
- Demonstrated separation between DNS failure and general connectivity failure

### Commands Used

```powershell
nslookup google.com
ping 8.8.8.8
```

---

# Scenario 3 — DHCP Failure Simulation

Simulated a DHCP renewal failure scenario.

The client failed to contact a DHCP server and automatically assigned itself an APIPA address (169.254.x.x), demonstrating understanding of DHCP lease acquisition and troubleshooting procedures.

### Result

- DHCP renewal timed out
- APIPA address assigned automatically
- Connectivity lost until static configuration was restored

### Commands Used

```powershell
ipconfig /release
ipconfig /renew
```

---

# Scenario 4 — Network Recovery

Restored proper static IP configuration and DNS settings to recover connectivity to both the domain controller and internet resources.

### Commands Used

```powershell
ping 192.168.1.10
ping google.com
nslookup google.com
```

---

# Scenario 5 — Network Diagnostics

Used common help desk troubleshooting tools to validate routing and name resolution.

### Commands Used

```powershell
tracert google.com
nslookup google.com
```

---

# Key Takeaways

This lab reinforced practical troubleshooting methodologies used in real-world IT support environments, including:

- Diagnosing DNS failures
- Understanding DHCP lease behavior
- Identifying APIPA addressing
- Recovering broken network configurations
- Using command-line diagnostic tools effectively

---

# Screenshots

## DNS Failure
![DNS Failure](screenshots/04-dns-failure-proof.png)

## DHCP Failure / APIPA Address
![DHCP Failure](screenshots/07-dhcp-failure-connecting.png)

## Network Restored
![Network Restored](screenshots/09-network-restored-successfully.png)

## NSLOOKUP Test
![NSLOOKUP](screenshots/nslookup-success.png)

## TRACERT Test
![TRACERT](screenshots/10-tracert-google.png)

## Domain Controller Connectivity
![Domain Connectivity](screenshots/11-domain-controller-ping.png)
