# GLPI Help Desk Lab

GLPI is deployed in a dedicated Proxmox LXC and used as a practical IT support and service-desk training environment.

## Purpose

The lab is designed to simulate common entry-level Help Desk work in a safe environment where I can practise:

- Ticket triage and prioritisation
- Assigning and updating incidents and requests
- Writing clear user-facing follow-ups
- Keeping internal troubleshooting notes
- Documenting solutions and resolutions
- Escalating issues when they require higher-level access or specialist knowledge
- Working through realistic support scenarios without affecting production systems

## Deployment

| Component | Details |
|---|---|
| Platform | Proxmox VE |
| Workload type | Linux Container (LXC) |
| LXC ID | `112` |
| Application | GLPI |
| Role | IT service management and Help Desk training |

Private addressing, credentials, mail settings, and other sensitive configuration are intentionally excluded from this public documentation.

## Help Desk Configuration

The GLPI environment currently includes:

- A Technician profile for support work
- Self-Service profiles for simulated end users
- ITIL ticket categories for common support areas
- A standard Help Desk ticket template
- Public follow-up templates for acknowledgement and information gathering
- Private internal troubleshooting-note templates
- Solution templates for resolved issues and temporary workarounds
- Simulated users and a queue of realistic incidents and service requests

The practice workflow follows a typical service-desk lifecycle:

```text
New
  -> Triage
  -> Assigned
  -> Processing
  -> Troubleshooting
  -> User communication
  -> Solution
  -> Solved
  -> Closed
```

## Practice Scenarios

The lab includes realistic scenarios such as:

- No internet access
- DNS resolution problems
- Outlook sending issues
- Forgotten Windows passwords
- PC boot loops and hardware faults
- Shared-drive access problems
- Printer issues
- Website/DNS failures
- New-user setup requests
- Slow Windows systems
- Suspicious/phishing email reports

These tickets are deliberately left unsolved at creation so I can work through the investigation and documentation process manually.

## Example: DNS Troubleshooting and Escalation

One practice incident involved a workstation that appeared connected to the network but could not load websites.

### Investigation

- Confirmed that the issue appeared isolated to one workstation.
- Collected the browser error reported by the user.
- Verified that IP connectivity was working by testing known external IP addresses.
- Used `nslookup` to test DNS resolution.
- Confirmed that queries to the workstation's assigned DNS server were timing out.
- Tested a known public DNS resolver directly and confirmed that name resolution worked through it.
- Used an alternate DNS resolver as a temporary workaround and confirmed that browsing was restored.

### Escalation Decision

The workstation-level issue was restored with a temporary workaround, but the failing upstream DNS service required investigation beyond the end-user device.

Rather than making unauthorised changes to shared network infrastructure, the issue would be escalated to the appropriate network or senior support technician with the diagnostic results already documented.

A useful escalation note would include:

- IP connectivity was successful.
- DNS queries to the assigned resolver timed out.
- DNS queries through an alternate resolver succeeded.
- Changing the workstation to the alternate resolver restored web access.
- The original DNS service or router configuration requires further investigation.

## What This Lab Teaches Me

This environment helps me practise not only technical troubleshooting, but also the parts of Help Desk work that are easy to overlook:

- Asking useful questions before making changes
- Isolating the scope of a fault
- Testing one layer at a time
- Communicating clearly with non-technical users
- Recording evidence instead of relying on memory
- Knowing when a workaround is not the same as a root-cause fix
- Knowing when to escalate rather than make a risky change

The goal is to build repeatable support habits that transfer to a real Help Desk or service-desk role.
