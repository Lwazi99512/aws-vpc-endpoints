# 🔒 AWS VPC Endpoints: Securing S3 Access

## Project Overview
Implemented **VPC Gateway Endpoints** to enforce private S3 access, blocking all public traffic.  
Key components:  
- VPC Endpoint (Gateway type for S3)  
- Restrictive Bucket Policy  
- Route Table configurations  

## Documentation
- **Visual Guide:** See screenshots in `/diagrams` folder.  
- **Full Technical Walkthrough:** [aws-networks-endpoints.pdf](aws-networks-endpoints.pdf)  

## Key Steps
1. Launched VPC, EC2, and S3 bucket  
2. Configured IAM access keys for EC2  
3. Created VPC endpoint for private S3 access  
4. Enforced bucket policy to restrict access to the endpoint  

## Lessons Learned
- **Route Tables Matter:** Forgot initial updates → access failures  
- **Least Privilege:** Bucket policies act as security bouncers  
- **AWS Quirks:** Hyphens vs. underscores in resource names matter  

## Quick Test Command
```bash
aws s3 ls s3://your-bucket --endpoint-url https://vpce-12345.s3.us-east-1.vpce.amazonaws.com
