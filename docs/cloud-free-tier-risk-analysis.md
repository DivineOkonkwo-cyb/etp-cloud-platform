# AWS Free Tier Risk Analysis

This document highlights common AWS Free Tier billing traps and provides guidance to prevent unexpected charges.

---

## 1. EC2 Runtime
**Why cost happens:** Running EC2 instances beyond the Free Tier limit (750 hours/month per instance) incurs hourly charges.  
**Prevention method:** Monitor instance uptime, terminate instances when not in use.  
**Console verification path:** EC2 → Instances → Check instance state and launch time.

---

## 2. EBS (Elastic Block Store)
**Why cost happens:** Additional storage or unattached volumes accumulate charges.  
**Prevention method:** Delete unused volumes and snapshots; use Free Tier eligible sizes only.  
**Console verification path:** EC2 → Elastic Block Store → Volumes.

---

## 3. Elastic IP
**Why cost happens:** Elastic IPs not associated with a running instance are billed per hour.  
**Prevention method:** Release unused Elastic IP addresses.  
**Console verification path:** EC2 → Network & Security → Elastic IPs.

---

## 4. NAT Gateway
**Why cost happens:** NAT Gateway usage and data transfer are billed hourly and per GB.  
**Prevention method:** Avoid unnecessary NAT Gateways in Free Tier experiments. Use public subnet for minimal setups.  
**Console verification path:** VPC → NAT Gateways.

---

## 5. CloudWatch Logs
**Why cost happens:** Storing logs beyond Free Tier limits (5 GB/month) results in charges.  
**Prevention method:** Configure retention policies, delete old logs regularly.  
**Console verification path:** CloudWatch → Logs → Log groups → Check usage and retention.

---

**Summary:**  
Careful monitoring and disciplined resource cleanup prevent unexpected AWS Free Tier costs. Always verify usage via the **Billing Dashboard** and apply retention or termination policies where appropriate.

