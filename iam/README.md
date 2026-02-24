Week2: Add IAM explanation
# IAM Policy Explanation

## Least Privilege
The IAM policy follows the principle of least privilege by granting only the necessary permission, `s3:GetObject`, to access the specified S3 bucket and its objects. This minimizes security risk by preventing users or applications from performing unauthorized actions, such as deleting or modifying data.

## Static Key Risk
Using long-lived static access keys can pose a security threat if the keys are leaked or compromised. Attackers could gain full access to the assigned permissions, potentially causing data loss or exposure. Mitigation strategies include rotating keys regularly, storing them securely, or avoiding static keys entirely by using IAM roles.

## IAM Role Benefit
IAM roles provide temporary credentials that automatically expire, eliminating the need for static keys. Roles enable secure, least-privilege access for users, applications, or services, and can be attached to EC2 instances, Lambda functions, or other AWS resources. This enhances security and simplifies access management.

---

**Summary:**  
By enforcing least privilege, avoiding static keys, and leveraging IAM roles, this approach reduces potential attack surfaces and aligns with AWS security best practices.
