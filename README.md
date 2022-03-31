# Cloud Security - AWS

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
    
