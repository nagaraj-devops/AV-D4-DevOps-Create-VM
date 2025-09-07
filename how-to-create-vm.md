🛠️ Steps to Create a VM on AWS (EC2)
1. Log in

  - Go to AWS Management Console.
  - Sign in with your AWS account.

2. Open EC2 Service

  - From the AWS console → Search for EC2 → Click EC2 Dashboard.
  - Click Launch Instance.

3. Choose an Amazon Machine Image (AMI)

  - Select the operating system you want for your VM:
  
    - Amazon Linux 2    
    - Ubuntu Server    
    - Windows Server    
    - RedHat, etc.

4. Choose an Instance Type

  - Select CPU/RAM configuration.
  
    - Example:  
    - t2.micro (1 vCPU, 1 GB RAM) → Free tier eligible.  
    - Larger sizes available for production workloads.

5. Configure Instance Details

  - Number of instances.  
  - Networking (VPC, Subnet, Public IP).  
  - IAM role (if needed).

6. Add Storage

  - Default: 8 GB EBS volume.  
  - Can increase if needed (e.g., 30 GB).

7. Add Tags (Optional)

  - Key: Name, Value: MyFirstVM → Helps you identify the instance.

8. Configure Security Group

  - Security group = firewall rules.
  
    - Add rules:  
    - SSH (22) → if Linux.  
    - RDP (3389) → if Windows.  
    - HTTP (80), HTTPS (443) → if web server.

9. Review and Launch

  - Click Launch.
  - AWS asks for a Key Pair (for SSH login):
  - Create a new key pair → Download .pem file (very important, only one chance).
    - Example: mykey.pem.

10. Connect to Your VM

  - Wait until Instance State = Running.  
  - Get the Public IP address from EC2 dashboard.  
  - Connect via SSH (Linux/Mac/Windows PowerShell):
  
      chmod 400 mykey.pem
      ssh -i mykey.pem ubuntu@<EC2-PUBLIC-IP>
  
  
  (Use ec2-user for Amazon Linux, ubuntu for Ubuntu, admin for Windows RDP login).

✅ Done! You now have a virtual machine (VM) running on AWS 🎉
