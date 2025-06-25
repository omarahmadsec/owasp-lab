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

## 🪝 Stored XSS

**Challenge:** Post a review that executes JavaScript when viewed.  
**Vulnerability:** Stored Cross-Site Scripting (XSS)

**Steps:**
1. Go to product page and leave a review:
   ```html
   <script>alert('XSS')</script>

    View the product page again — the script executes.

🧬 Sensitive Data Exposure

Challenge: View the admin's email and password hash.
Vulnerability: Information Disclosure

Steps:

    Open Developer Tools → Application → Storage → Local Storage

    Check tokens and user object: email, password, and JWTs are often exposed.

📁 Directory Traversal

Challenge: Access restricted server files.
Vulnerability: Path Traversal

Steps:

    Go to /ftp/ endpoint

    Try accessing files like:

    /ftp/../../../../etc/passwd

💥 Command Injection

Challenge: Execute a command on the server.
Vulnerability: Remote Code Execution (RCE)

Steps:

    Find feedback or search input

    Try payloads like:

    ; ping -c 4 127.0.0.1

✅ Tips

    Use Burp Suite to intercept and modify requests

    Keep an eye on hidden APIs with DevTools or ZAP

    Capture flags for each completed challenge in Juice Shop UI

📎 Resources

    Official Juice Shop

    OWASP Cheat Sheet Series
