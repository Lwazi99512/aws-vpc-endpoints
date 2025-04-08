# 🔒 AWS VPC Endpoints: Securing S3 Access

## Project Overview
Used **VPC Gateway Endpoints** to enforce private S3 access, blocking all public traffic.  

## Key Components
- **VPC Endpoint** (Gateway type for S3)  
- **Bucket Policy** with `Deny` rules  
- **Route Table** updates  

## Documentation
- **Screenshots:** See `/diagrams` folder for setup visuals.  
- **Detailed steps:** [`vpc-endpoints-guide.pdf`](vpc-endpoints-guide.pdf) *(attached separately)*  

## Quick Command
```bash
# Test endpoint access:
aws s3 ls s3://your-bucket --endpoint-url https://vpce-12345.s3.us-east-1.vpce.amazonaws.com
