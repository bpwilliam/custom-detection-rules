# custom-detection-rules
This repo will be to hold my custom detection rules I created while training in a home lab.  These are examples for hiring managers to review to assess my capability to work for them.

All of these detections were created from the botsv3 dataset in Splunk.

aws_bucket_misconfigurations.spl
Built a custom detection rule to catch exposed AWS S3 buckets. It spots risky public ACLs, filters out intended public buckets using naming rules, and groups alerts by source IP to cut down noise for security teams.

aws_cloud_authentications_privileged_accounts, azure_cloud_authentications_privileged_accounts.spl
Built a detection rule to track privileged user logins to the AWS and Azure consoles, helping stop cybercriminals before they cause damage.

aws_createaccesskey_by_nonprivilegedidentities.spl
Built a new AWS detection rule. It flags when a non-admin user creates an access key. This helps catch compromised accounts early before hackers use those keys for malicious actions.

aws_securitygroup_misconfiguration_inbound.spl
Built a custom detection rule to catch exposed AWS S3 buckets. It spots risky public ACLs, filters out intended public buckets using naming rules, and groups alerts by source IP to cut down noise for security teams.

aws_terminate_instances.spl
Built a new detection rule to stop mass AWS resource deletions during destructive cyberattacks. Inspired by recent 2026 threat tactics, this rule flags unusual spikes in EC2 termination calls, filters out routine service accounts, and rolls up alerts by user identity to stop alert fatigue.

cloud_aws_infrastructure_discovery.spl
Built a custom detection rule to catch AWS reconnaissance and environment mapping before threat actors can move further down the cyber kill chain.

command_and_control_long_urls.spl
Built a new detection rule to spot sneaky command-and-control (C2) traffic hiding in unusually long outbound URLs. Attackers use long query strings to stealthily exfiltrate data or push execution commands to compromised assets.

gigawiper_malware_processes.spl
Developed a detection rule for the new Gigawiper Windows backdoor based on CTI from The Hacker News, focusing on takeown and icacls commands targeting system processes. The rule utilizes regex filtering, scheduled maintenance windows to reduce false positives, and machine-level IP correlation to minimize alert fatigue.  Used a lookup of epoch timestamps representing the maintenance start and end dates for each machine.

web_byte_volume_mismatch.spl
Built a custom detection rule to spot abnormal data exfiltration by analyzing incoming-to-outgoing HTTP/HTTPS traffic ratios, filtering out enterprise noise, and grouping alerts by IP pairs to reduce analyst fatigue and catch potential insider or outsider data theft early.
