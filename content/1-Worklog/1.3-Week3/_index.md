---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Understand and implement Hybrid Cloud networking model on AWS.
* Set up Amazon Transit Gateway to connect multiple VPCs.
* Configure Hybrid DNS using Amazon Route 53 Resolver for name resolution between AWS and on-premises environments.

### Tasks Implemented This Week:

| Day | Tasks | Start Date | End Date | Reference |
| --- | ----- | ---------- | -------- | --------- |
| 2   | - Study the concept and functions of Transit Gateway<br>- Create multiple VPCs | 04/05/2026 | 04/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3   | - Create Transit Gateway<br>- Configure ASN and DNS support<br>- Create Transit Gateway Attachments to connect VPCs<br>- Create Transit Gateway Route Tables | 05/05/2026 | 05/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4   | - Configure route tables for each subnet<br>- Add routes from VPCs to Transit Gateway<br>- Test connectivity between VPCs using ping | 06/05/2026 | 06/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5   | - Deploy infrastructure using CloudFormation Templates<br>- Configure Security Groups for DNS, RDP, and SSH<br>- Create Route 53 Outbound Endpoint and Resolver Rules | 07/05/2026 | 07/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6   | - Create Route 53 Inbound Endpoints<br>- Test routing and DNS operation<br>- Clean up resources to avoid unnecessary charges:<br>&emsp; + Delete Resolver Rules<br>&emsp; + Delete Endpoints<br>&emsp; + Delete Transit Gateway Attachments<br>&emsp; + Delete Transit Gateway and Route Tables | 08/05/2026 | 08/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

### Week 3 Achievements:

* Successfully deployed Amazon Transit Gateway to connect multiple VPCs within the same network system.
* Configured routing between VPCs through Transit Gateway and successfully tested connectivity using ping.
* Deployed infrastructure using CloudFormation Templates for the Hybrid DNS model.
* Successfully set up Hybrid DNS using Amazon Route 53 Resolver.
* Created and configured:
  * Route 53 Outbound Endpoint
  * Route 53 Inbound Endpoint
  * Resolver Rules
