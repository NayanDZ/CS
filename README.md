# Cloud Computing and Security
Cliud Computing is Internet based computing where shared resources, software, and information provided to computers and other devices on demand.

Deployment models of cloud computing
- Saas(Software as  service)
  - Software offering in the cloud (Windows live, Gmail, ZOHO)
- Paas(Platform as service)
  - Platform offering in the cloud (Windows Azure, AWS, Google’s App Engine)
- Iaas(Infrastructure as service)
  - Infrastructure offering in the cloud(VMware, IBM, GoGrid, Flexiscale)


**Cloud security Top-10 Risk**

1. R1-Accountability and Data ownership
2. R2-User Identity Federation
3. R3-Regulatory Compliance
4. R4-Business Continuity and Resiliency
5. R5-User Privacy and Secondary Usage of Data
6. R6-Service and Data Integration
7. R7-Multi Tanancy and Physical Security
8. R8-Incidence Analysis and Forensic Support
9. R9-Infrastructure Security
10. R10-Not Production Environment Exposure

### Cloud Vulnerability
1. Cloud Misconfiguration
   - Identity and Access Management
     - Enforce the principle of least privilege for all of your cloud resources and users; avoid granting complete access to a resource if a service only needs read access or access to a subpart of the resource.
     - Use third-party tools to scan and detect misconfiguration of IAM policies; cloud-native application protection platform (CNAPP) can help increase the visibility of a misconfiguration.
     - Frequently review access and privileges, as requirements change over time.
   - Public Data Stoage
   - Other Misconfigurations
     - Always use HTTPS instead of HTTP also FTP instead of SFTP).
     - Restrict all inbound and outbound ports if not needed.
     - Keep secrets like API keys, passwords, etc. in one and only one place using a secure secret management solution (e.g., AWS Secrets Manager).
2. Insecure APIs
   - Implement web application firewall (WAF) to filter requests by IP address or HTTP header info, and to detect code injection attacks; WAFs also let you set response quotas per user or other metrics.
4. Lack of Vusibility
5. Lack of Multi-factor Authentication
6. Malicious Insiders
7. Distributed Denial-of-service attacks
   
## Cloud Security - AWS

##### What is a AWS S3 bucket? - > it is Amazone's SIMPLE | STORAGE | SERVICE
##### What is Amazon EC2 -> Elastic Computing Cloud (EC2) is a virtual server that can be used to run applications on AWS

### Passive Recon

- **How to find company use AWS like. S3 bucket or ec2**

  Step-1. Find IP address of website -> ``$ ping zoho.com  ``
  
  Step-2. Find AWS Region or URL using Nslookup -> `` $ nslookup zoho.com `` (AWS Region is a geographica location which AWS provide multipe physical location)
  e.g. ***s3-website-us-west-2.amazonaws.com***  || ***ec2-website-us-west-2.amazonaws.com***
  
  ![image](https://user-images.githubusercontent.com/65315090/161034702-f51736f2-c0f3-4b98-8e96-1d68554aa839.png)
  
  
  ![image](https://user-images.githubusercontent.com/65315090/161034275-a2a64592-c147-4937-93aa-49411384c830.png)
  IF us get Name *.cloudfront.net it meens name resolution is protected by cloudfront.net

### Active Recon

- **Find S3 bucket URL**
  URL Structure like: ***https://bucketname.s3.amazon.com***

  - Tool: nahamsec/lazys3 (Bruteforcing-use world list)
    ```$ ruby lazys3.rb zoho.com```

  - Tool: AWS CLI (To identify all Amazon S3 buckets with website configuration enabled)
    ```$ aws s3 LS s3://zoho.com --no-sign-request --region us-west-2```
### Tools
- Configuration Review
  - Prowler [https://github.com/prowler-cloud/prowler] (Open Source security tool to perform AWS, GCP and Azure security)
  - Azure-CIS [https://github.com/rallyspeed/Azure-CIS]
