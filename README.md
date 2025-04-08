# 🔐 AWS VPC Endpoints: Locking Down S3 Access  

**Goal:** Restrict S3 bucket access to ONLY my VPC using Gateway Endpoints—no internet randoms allowed.  

## 📸 Proof  
Screenshots in [`/diagrams`](diagrams/):  
- [VPC Endpoint Config](diagrams/vpc-config.png)  
- ["Access Denied" Error](diagrams/error.png) *(before fix)*   

## 🛠️ How It Works  
1. **Created a VPC Endpoint** (like a private tunnel to S3).  
2. **Wrote a Bucket Policy** to block all traffic except from my VPC.  
3. **Tested It:**  
   - ✅ EC2 in my VPC could access S3.  
   - ❌ External requests got denied.  

## 💡 Lessons Learned  
- **Route Tables Matter:** Forgot to update them at first—total fail.  
- **Least Privilege:** Bucket policies are bouncers for your data.  
- **AWS is Picky:** Hyphens vs. underscores in filenames break things.  

## 🚀 Try It Yourself  
```bash
# Command I used to test access:
aws s3 ls s3://my-bucket --endpoint-url https://vpce-12345.s3.us-east-1.vpce.amazonaws.com
