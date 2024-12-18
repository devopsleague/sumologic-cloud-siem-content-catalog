# [Rules](README.md): Outlier in Data Outbound Per Hour by Admin or Sensitive Device

## Description
A larger than typical amount of data has been observed being sent outbound from a Sensitive Device or an Admin user. It is recommended to investigate the device associated with this IP, the Internet destinations and traffic associated with this anomalous behavior. A normalized record search for the source IP and external network traffic, within the period of time of the detection will help identify suspicious activity. This rule is dependent on the Match Lists "domain_controllers" and "admin_usernames" being populated with the sensitive device IPs and admin usernames. Additionally, Entity Tagging offers a similar and extensible alternative to Match Lists. To add more sensitive Match Lists, or Entity Tagging, please use Rule Tuning Expressions. For further customization, consider adjusting the severity of this rule and/or using entity severity as needed to increase the severity of this rule.

## Additional Details
|Detail|Value|
|----|----|
|Type|Outlier|
|Category|Exfiltration|
|Apply Risk to Entities|srcDevice_ip, user_username|
|Signal Name|Hourly Outlier in Outbound Data Sent from Sensitive Device or Admin User - Source IP: {{srcDevice_ip}}|
|Summary Expression|A larger than typical amount of data was observed sent outbound from IP: {{srcDevice_ip}}and User: {{user_username}}|
|Retention Window|2592000000|
|Baseline Window|1209600000|
|Standard Deviation Threshold|3|
|Floor Value|100000000|
|Score/Severity|Static: 0|
|Enabled by Default|True|
|Prototype|False|
|Tags|_mitreAttackTechnique:T1030, _mitreAttackTechnique:T1071, _mitreAttackTechnique:T1567, _mitreAttackTactic:TA0010, _mitreAttackTactic:TA0011|
## Vendors and Products


## Fields Used

|Origin|Field|
|----|----|
|Normalized Schema|bytesOut|
|Normalized Schema|dstDevice_ip_isInternal|
|Normalized Schema|listMatches|
|Normalized Schema|objectClassification|
|Normalized Schema|srcDevice_ip|
|Normalized Schema|srcDevice_ip_isInternal|
|Normalized Schema|user_username|


