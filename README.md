# Multi-Account AWS Governance using AWS Organizations & SCP

## 📌 Project Overview

This project demonstrates how to implement centralized governance across multiple AWS accounts using:

* AWS Organizations
* Organizational Units (OUs)
* Service Control Policies (SCPs)

It helps enforce **security, cost control, and compliance policies** across Dev, Test, and Production environments.

---

## 🎯 Objective

* Organize AWS accounts using OUs
* Apply centralized policies using SCPs
* Prevent unauthorized and risky actions
* Ensure compliance across all accounts

---

## 🏗️ Architecture

```
AWS Organization
│
├── Dev OU
│   └── Dev Account
├── Test OU
│   └── Test Account
└── Prod OU
    └── Prod Account
```

SCPs are applied at OU and Root level.

---

## ⚙️ Technologies Used

* AWS Organizations
* Service Control Policies (SCP)
* IAM
* CloudTrail

---

## 🚀 Implementation Steps

### 1. AWS Organization Setup

* Create Organization
* Enable All Features
* Create OUs (Dev, Test, Prod)
* Move accounts under respective OUs

---

### 2. Create SCP Policies

* Restrict large EC2 instances in Dev
* Prevent disabling CloudTrail
* Restrict region usage

---

### 3. Attach Policies

* Dev OU → EC2 Restriction
* Root → CloudTrail Protection
* All OUs → Region Restriction

---

### 4. Validation

* Launch restricted EC2 → ❌ Denied
* Disable CloudTrail → ❌ Denied
* Use unapproved region → ❌ Denied

---

## 🔐 Sample SCP

```json
{
  "Effect": "Deny",
  "Action": "ec2:RunInstances",
  "Resource": "*"
}
```

---

## 📊 Benefits

* Centralized governance
* Cost control
* Improved security
* Compliance enforcement

---

## 📸 Screenshots

* OU Structure
* SCP Policies
* Denied Actions
* CloudTrail Logs

(Add screenshots here)

---

## 📌 Conclusion

This project provides a scalable and secure governance model for managing multiple AWS accounts using AWS-native services.

---

## 🔗 Author

Pruthviraj Desai
