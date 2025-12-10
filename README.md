# Metasploit RC Templates Repository

**For Training Use – Non-functional Templates**

This repository contains safe, educational Metasploit RC (Resource) file templates for cybersecurity learning and VirtualBox lab environments.

## ⚠️ IMPORTANT NOTICE
All RC files in this repository contain **PLACEHOLDER VALUES ONLY** and are **NON-OPERATIONAL**. They are designed for educational purposes to help understand Metasploit Framework structure and syntax.

## Repository Structure

```
msf_rc_templates/
├── handlers/          # Payload handler templates
├── exploits/          # Exploit module templates
├── scanners/          # Network scanning templates
├── auxiliary/         # Auxiliary module templates
├── post/              # Post-exploitation templates
├── enumeration/       # Information gathering templates
├── web/               # Web application testing templates
├── wireless/          # Wireless security templates
├── database/          # Database testing templates
├── cloud/             # Cloud security templates
├── mobile/            # Mobile security templates
├── privesc/           # Privilege escalation templates
├── persistence/       # Persistence mechanism templates
├── evasion/           # Evasion and obfuscation templates
├── network/           # Network attack templates
├── activedirectory/   # Active Directory attack templates
├── container/         # Container security templates
├── iot/               # IoT and embedded device templates
├── socialeng/         # Social engineering templates
├── forensics/         # Forensics and anti-forensics templates
├── reporting/         # Report generation templates
├── utility/           # Utility and helper templates
├── cleanup/           # Cleanup and reset templates
├── workspace/         # Workspace management templates
└── templates/         # Base template examples
```

## Usage Instructions

### Quick Start
1. **Copy Template**: Select an appropriate RC template
2. **Replace Placeholders**: Fill in actual values for your lab environment
3. **Load in MSF**: Use `resource <filename>.rc` in msfconsole
4. **Study Structure**: Analyze the command flow and syntax

### Detailed Usage Guide

#### Step 1: Setup Metasploit
```bash
# Start PostgreSQL database
sudo systemctl start postgresql

# Initialize MSF database
sudo msfdb init

# Start Metasploit console
msfconsole
```

#### Step 2: Prepare Templates
```bash
# Clone or download templates
git clone <repository_url>
cd msf_rc_templates

# Copy template to working directory
cp handlers/reverse_tcp_handler.rc /tmp/my_handler.rc
```

#### Step 3: Configure Templates
Edit the RC file and replace placeholders:
```bash
# Example: Edit handler template
nano /tmp/my_handler.rc

# Replace:
# <LHOST> with your IP (e.g., 192.168.1.100)
# <LPORT> with your port (e.g., 4444)
# <TARGET_IP> with target IP (e.g., 192.168.1.200)
```

#### Step 4: Load in Metasploit
```bash
# In msfconsole:
msf6 > resource /tmp/my_handler.rc

# Or load multiple files:
msf6 > resource /tmp/handler.rc
msf6 > resource /tmp/scanner.rc
msf6 > resource /tmp/exploit.rc
```

#### Step 5: Monitor Results
```bash
# Check active jobs
msf6 > jobs -l

# Check sessions
msf6 > sessions -l

# Interact with session
msf6 > sessions -i 1
```

### Advanced Usage

#### Batch Processing
```bash
# Create master RC file
echo "resource /root/handlers.rc" > /tmp/master.rc
echo "resource /root/scanners.rc" >> /tmp/master.rc
echo "resource /root/exploits.rc" >> /tmp/master.rc

# Load master file
msf6 > resource /tmp/master.rc
```

#### Automated Scanning
```bash
# Set global variables first
msf6 > setg RHOSTS 192.168.1.0/24
msf6 > setg LHOST 192.168.1.100
msf6 > setg WORKSPACE lab_test

# Then load templates
msf6 > resource scanners/port_scanner.rc
```

#### Database Integration
```bash
# Setup workspace
msf6 > workspace -a pentest_lab
msf6 > workspace pentest_lab

# Run Nmap integration
msf6 > resource scanners/nmap_integration.rc

# View results
msf6 > hosts
msf6 > services
```

## Placeholder Format

All templates use consistent placeholder formatting:
- `<TARGET_IP>` - Target host IP address
- `<TARGET_PORT>` - Target service port
- `<LHOST>` - Local host for reverse connections
- `<LPORT>` - Local port for handlers
- `<EXPLOIT_MODULE>` - Exploit module path
- `<PAYLOAD_TYPE>` - Payload selection
- `<SESSION_ID>` - Session identifier

## Template Guide

### Handler Templates
- `reverse_tcp_handler.rc` - Basic reverse TCP handler
- `bind_tcp_handler.rc` - Bind TCP handler
- `multi_handler.rc` - Multi-handler with encoding
- `https_handler.rc` - HTTPS encrypted handler
- `dns_handler.rc` - DNS tunneling handler

### Exploit Templates
- `windows_exploit_template.rc` - Windows exploit framework
- `linux_exploit_template.rc` - Linux exploit framework
- `web_exploit_template.rc` - Web application exploits
- `buffer_overflow_template.rc` - Buffer overflow exploits
- `multi_platform_exploit.rc` - Cross-platform exploits
- `eternalblue.rc` - MS17-010 EternalBlue exploit
- `eternalromance.rc` - MS17-010 EternalRomance exploit
- `eternalchampion.rc` - MS17-010 EternalChampion exploit
- `eternalsynergy.rc` - MS17-010 EternalSynergy exploit
- `doublepulsar.rc` - DoublePulsar backdoor exploit
- `wannacry.rc` - WannaCry ransomware-style exploit
- `petya.rc` - Petya ransomware-style exploit
- `badrabbit.rc` - BadRabbit ransomware-style exploit
- `bluekeep.rc` - CVE-2019-0708 BlueKeep RDP exploit
- `zerologon.rc` - CVE-2020-1472 Zerologon exploit
- `printnightmare.rc` - CVE-2021-1675 PrintNightmare exploit
- `smbghost.rc` - CVE-2020-0796 SMBGhost exploit
- `shellshock.rc` - Bash Shellshock vulnerability
- `heartbleed.rc` - OpenSSL Heartbleed vulnerability
- `log4j.rc` - Log4Shell vulnerability
- `struts2.rc` - Apache Struts2 vulnerability
- `conficker.rc` - MS08-067 Conficker worm exploit
- `blaster.rc` - MS03-026 Blaster worm exploit
- `sasser.rc` - MS04-011 Sasser worm exploit
- `slammer.rc` - MS02-039 SQL Slammer exploit
- `nimda.rc` - MS01-023 Nimda worm exploit
- `codered.rc` - MS01-033 Code Red worm exploit
- `stuxnet.rc` - MS10-061 Stuxnet-style exploit
- `flame.rc` - Flame malware-style exploit
- `duqu.rc` - Duqu malware-style exploit

### Scanner Templates
- `port_scanner.rc` - TCP port scanning
- `service_scanner.rc` - Service enumeration
- `vulnerability_scanner.rc` - Vulnerability assessment
- `stealth_scanner.rc` - Low-profile scanning
- `nmap_integration.rc` - Nmap database integration

### Post-Exploitation Templates
- `system_info.rc` - System information gathering
- `privilege_escalation.rc` - Privilege escalation
- `persistence.rc` - Maintain access
- `credential_dump.rc` - Extract credentials
- `network_pivot.rc` - Network pivoting
- `keylogger.rc` - Keystroke capture
- `screenshot.rc` - Screen capture

### Auxiliary Templates
- `brute_force_ssh.rc` - SSH brute force
- `brute_force_smb.rc` - SMB brute force
- `ftp_brute.rc` - FTP brute force
- `telnet_brute.rc` - Telnet brute force
- `rdp_brute.rc` - RDP scanning
- `vnc_brute.rc` - VNC brute force
- `snmp_brute.rc` - SNMP community strings

### Web Application Templates
- `web_scanner.rc` - Web directory scanning
- `sql_injection.rc` - SQL injection testing
- `cms_scanner.rc` - CMS vulnerability scanning
- `ssl_scanner.rc` - SSL/TLS security testing

### Enumeration Templates
- `network_enum.rc` - Network discovery
- `smb_enum.rc` - SMB enumeration
- `dns_enum.rc` - DNS enumeration
- `ldap_enum.rc` - LDAP enumeration

### Privilege Escalation Templates
- `windows_local_exploits.rc` - Windows local privilege escalation
- `linux_kernel_exploits.rc` - Linux kernel exploits
- `uac_bypass.rc` - UAC bypass techniques

### Persistence Templates
- `registry_persistence.rc` - Registry-based persistence
- `service_persistence.rc` - Service-based persistence
- `scheduled_task.rc` - Scheduled task persistence

### Evasion Templates
- `av_evasion.rc` - Antivirus evasion techniques
- `encoding_chains.rc` - Payload encoding chains
- `process_injection.rc` - Process injection methods

### Network Attack Templates
- `mitm_attacks.rc` - Man-in-the-middle attacks
- `dns_attacks.rc` - DNS spoofing and attacks
- `dhcp_attacks.rc` - DHCP attacks and poisoning

### Active Directory Templates
- `kerberoasting.rc` - Kerberoasting attacks
- `golden_ticket.rc` - Golden ticket attacks
- `dcsync.rc` - DCSync attacks

### Container Security Templates
- `docker_escape.rc` - Docker container escape
- `kubernetes_attacks.rc` - Kubernetes security testing

### IoT/Embedded Templates
- `router_exploits.rc` - Router and network device exploits
- `scada_attacks.rc` - SCADA/ICS security testing

### Social Engineering Templates
- `phishing_attacks.rc` - Phishing attack frameworks
- `hta_attacks.rc` - HTA-based attacks
- `macro_attacks.rc` - Macro-based document attacks

### Forensics Templates
- `evidence_collection.rc` - Digital evidence collection
- `timestomp.rc` - Anti-forensics techniques

### Reporting Templates
- `report_generation.rc` - Automated report generation
- `automated_documentation.rc` - Documentation automation

### Utility Templates
- `payload_generator.rc` - Payload generation
- `encoder_template.rc` - Payload encoding
- `session_cleanup.rc` - Session management
- `workspace_setup.rc` - Workspace configuration

## Common Placeholders

| Placeholder | Description | Example | Required |
|-------------|-------------|---------|----------|
| `<TARGET_IP>` | Target host IP | 192.168.1.100 | Yes |
| `<TARGET_RANGE>` | IP range | 192.168.1.0/24 | Yes |
| `<LHOST>` | Local host IP | 192.168.1.50 | Yes |
| `<LPORT>` | Local port | 4444 | Yes |
| `<SESSION_ID>` | Session number | 1 | Yes |
| `<DNS_HOST>` | DNS server | 8.8.8.8 | Optional |
| `<CLIENT_ID>` | Cloud client ID | abc123 | Optional |
| `<ACCESS_TOKEN>` | API token | token123 | Optional |

### Example Replacements
```bash
# Before (template):
set RHOST <TARGET_IP>
set LHOST <LHOST>
set LPORT <LPORT>

# After (configured):
set RHOST 192.168.1.100
set LHOST 192.168.1.50
set LPORT 4444
```

## Learning Objectives

- Understand Metasploit RC file syntax
- Learn automation workflows
- Practice module configuration
- Study attack chain sequences
- Explore framework capabilities

## Troubleshooting

### Common Issues

**Template won't load:**
```bash
# Check file path
msf6 > resource /full/path/to/file.rc

# Check file permissions
chmod +r template.rc
```

**Module not found:**
```bash
# Update Metasploit
sudo msfupdate

# Search for module
msf6 > search ms17_010
```

**Payload fails:**
```bash
# Check network connectivity
ping <TARGET_IP>

# Verify firewall settings
sudo ufw status
```

**Database errors:**
```bash
# Restart database
sudo systemctl restart postgresql
msf6 > db_rebuild_cache
```

## Safety Guidelines

- ⚠️ All templates contain placeholders only
- 🔒 Only use in authorized lab environments
- 📚 Educational purposes only
- 🛡️ Follow responsible disclosure practices
- 🚫 Never use against unauthorized targets
- 📝 Always document your testing activities

---
**Educational Use Only - VirtualBox Lab Environment**