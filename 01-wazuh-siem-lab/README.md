# Wazuh SIEM Home Lab

I deployed Wazuh on my Proxmox home lab, enrolled Windows and macOS endpoints, and tested a custom rule for repeated failed Windows logins.

## Deployment verification

### Wazuh services on Harrenhal

I verified that the Wazuh manager, indexer and dashboard were all running on Harrenhal.

![Wazuh manager running on Harrenhal](evidence/01a-wazuh-manager.png)
![Wazuh indexer and dashboard running](evidence/01b-wazuh-indexer-dashboard.png)

### Endpoint monitoring

The dashboard showed both enrolled agents as active: IMALABI on Windows 11 and Malabi-MBP on macOS.

![Windows and macOS agents active in Wazuh](evidence/02-agents-active.png)

### Windows failed-login detection

I configured rule 100100 to raise a level 10 alert after five failed Windows logins within 120 seconds.

![Custom rule 100100 showing its threshold and timeframe](evidence/03-custom-rule.png)

On 25 November 2026, Wazuh recorded a level 10 alert from IMALABI. The alert shows the rule description used at the time of the test. I later updated the wording to “5 failed Windows logins within 2 minutes.”

![Level 10 alert from IMALABI for rule 100100](evidence/04-alert-triggered.png)