# 🍊 OWASP Juice Shop – Walkthrough

This document includes a series of solved challenges from OWASP Juice Shop, demonstrating various common web vulnerabilities from the OWASP Top 10 list.

---

## 🔓 Login Bypass

**Challenge:** Log in as the administrator without knowing the password.  
**Vulnerability:** Authentication Bypass / SQL Injection

**Steps:**
1. Go to login page
2. Enter payload:  
   **Username:** `admin'--`  
   **Password:** (leave blank)
3. You’re logged in as the admin user.

---
