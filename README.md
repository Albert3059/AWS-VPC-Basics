# VPC Tutorial Overview

This GitHub page provides a tutorial on understanding traffic flow into an EC2 instance by experimenting with **Security Groups** and **Network Access Control Lists (NACLs)** within a **Virtual Private Cloud (VPC)**. Below is a summary of the main sections and findings:

---

## 1. Setup and Initial Configuration

### EC2 Instance Placement
- The EC2 instance is placed in a **public subnet** within the VPC.

### Application Setup
- A Python application is installed and run on the EC2 instance using the command:
  ```bash
  python3 -m http.server 8000
  ```

---

## 2. Security Group (SG)

### Role
- Acts as the **last layer of defense** for controlling inbound and outbound traffic to the EC2 instance.

### Test 1: Port 8000 Not Allowed
- Initially, port 8000 is **not allowed** in the security group.
- **Result**: The application is **not accessible** because the security group blocks traffic on port 8000.

### Test 2: Port 8000 Allowed
- Port 8000 is **explicitly allowed** in the security group.
- **Result**: The application becomes **accessible** as the security group now permits traffic on port 8000.

---

## 3. Network Access Control List (NACL)

### Role
- Acts as the **first layer of defense** for controlling traffic at the subnet level.

### Test 1: Port 8000 Blocked at NACL Level
- Port 8000 is **blocked** at the NACL level.
- **Result**: The application is **not accessible** because the NACL prevents traffic on port 8000.

---

## Conclusion

This tutorial highlights the importance of correctly configuring both **Security Groups** and **NACLs** to control access to applications running on EC2 instances within a VPC. Proper configuration ensures that traffic flows as intended while maintaining security.

---
