AWS
-S3 are Amazon's primary storage service to host files or other large objects.  Intelligent tiering  to switch between "infrequent access" and "standard access".  S3 Glacier for archivals and NOT user facing content.  Standard Retrieval fees apply
REF: https://www.cloudsavvyit.com/2329/aws-s3-pricing-explained-tiered-storage-can-save-you-money/
-BottleRocket is a focused platform for running Docker containers only similar to lightweight hypervisors like Hyper-V, VMWare, or Proxmox but instead of running other OSes, it runs containers.
-CloudTrail is an auditing, compliance monitoring, and governance tool.  Monitors the last 90 days free of charge, if you want to keep extending logs, you need to pay for the S3 storage logs per 100,000 events logged
--
Lock down AWS resources
-I haven't logged into my AWS account for a while so I needed up update the root password.  I also setup MFA as mentioned in the article.
-I do not regularly use EC2 instances but I updated the Firewall to allow incoming from my IP address by going into Security Groups and editing "Inbound rules" for SSH to include "myIP"
REF: https://www.cloudsavvyit.com/436/how-to-lock-down-your-aws-resources/
--
-AWS Lambda is serverless?  Serverless is not actually serverless just management of the server is taken away which is great for programmers but can be intimidating to them.  It is actually a bit easy: write some code, copy generic docker file, deploy
--
Simple Storage Service (S3) buckets are secure storage but not encrypted
Elastic Compute Cloud (EC2) servers in the cloud, scalable hence the elastic term but customer needs to secure
--


AZURE
Azure Security Basics: Log Analytics, Security Center, and Sentinel BHIS
-Advanced Threat Protection (ATP)
-Log Analytics, Sentinel, and ATP can produce a complete picture of Azure authentication border defences, virtual server happenings, and other in between
-Deploy a VM or deploy a lab (APT Lab via Terraform) then click to Log Analytics workspaces dash
-cost can be about $2.40 per day each VM
-go to for tutorial: https://www.blackhillsinfosec.com/azure-security-basics-log-analytics-security-center-and-sentinel/
--
-Blobs are like AWS S3 buckets.  Folks are quick to go to new technologies but do not secure properly
--

MISC:
CLOUD SECURITY POSTURE
-There is a false belief that "cloud equals more secure" which is so pervasive that one of the largest cloud provider has an employee (retired senior FBI agent) whose job is to let clients know that system images are "no more secure than the servers and desktops they bought from Best Buy".  Chief Apology Officer (CAO).  Per SANS news

