# Vulnerability Assessment & Management Lab
A homelab repository documenting vulnerability scans, troubleshooting notes, and remediation write-ups from a controlled Proxmox-based lab environment.

## Table of Contents
- [Executive Summary](#executive-summary)
- [Lab Architecture](#lab-architecture)
- [Toolstack](#toolstack)
- [Assessment Workflow](#assessment-workflow)
- [Key Troubleshooting Lessons](#key-troubleshooting-lessons)
- [Write-Ups](#write-ups)
- [Disclaimer](#disclaimer)

## Executive Summary
This repository contains vulnerability assessment write-ups, network scan notes, and remediation documentation from a dedicated homelab environment. Using OpenVAS and the Greenbone Security Assistant (GSA), I performed vulnerability scans, reviewed findings, prioritized risks by severity, and documented practical remediation steps.

## Lab Architecture
All targets and scanning infrastructure are isolated within a virtual network protected by an OPNsense firewall to keep testing contained and safe.

- Hypervisor Platform: Proxmox VE
- Scanner Instance: Linux container hosting OpenVAS and GSA
- Target Network Subnet: `192.168.2.0/24`
- Sandbox Targets Deployed:
  - OWASP Juice Shop
  - Additional Linux and Windows lab targets

## Toolstack
- Vulnerability Scanner: OpenVAS / Greenbone Security Assistant (GSA)
- Reconnaissance: Nmap
- Packet Analysis: Wireshark
- Defensive Controls: OPNsense, AppArmor, UFW

## Assessment Workflow
1. Create a target in GSA for the lab host.
2. Create a scan task and assign the target.
3. Run the scan and wait for completion.
4. Review the report findings by severity.
5. Document the vulnerabilities and suggested remediation steps.

## Key Troubleshooting Lessons
During this lab, I resolved three major technical issues:
- VM resource allocation problems that prevented services from running properly.
- Web UI binding and access issues that limited remote access to GSA.
- LXC network misconfiguration where IPv4 was not set to DHCP, which prevented internet access.

## Write-Ups
- [Juice Shop Scan](writeups/juice-shop-scan.md)
- [OpenVAS Setup Notes](writeups/openvas-setup.md)
- [Proxmox Troubleshooting](writeups/proxmox-troubleshooting.md)

## Disclaimer
This repository is intended for educational and authorized lab use only. All scanning and testing were performed in a controlled environment.
