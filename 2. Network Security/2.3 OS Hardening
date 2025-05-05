# Cybersecurity Incident Report: OS Hardening
> OS hardening.

> Please visit this [link](https://www.coursera.org/learn/networks-and-network-security?specialization=google-cybersecurity) for further information. 

## Scenario

You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A disgruntled baker has decided to publish the website’s best-selling recipes for the public to access for free. 
The baker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website’s source code. They embedded a javascript function in the source code that prompted visitors to download and run a file upon visiting the website. After running the downloaded file, the customers are redirected to a fake version of the website where the seller’s recipes are now available for free.
Several hours after the attack, multiple customers emailed yummyrecipesforme’s helpdesk. They complained that the company’s website had prompted them to download a file to update their browsers. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly. 
In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.
To address the incident, you create a sandbox environment to observe the suspicious website behavior. You run the network protocol analyzer tcpdump, then type in the URL for the website, yummyrecipesforme.com. As soon as the website loads, you are prompted to download an executable file to update your browser. You accept the download and allow the file to run. You then observe that your browser redirects you to a different URL, greatrecipesforme.com, which is designed to look like the original site. However, the recipes your company sells are now posted for free on the new website. The logs show the following process:
1. The browser requests a DNS resolution of the yummyrecipesforme.com URL
2. The DNS replies with the correct IP address
3. The browser initiates an HTTP request for the webpage
4. The browser initiates the download of the malware
5. The browser requests another DNS resolution for greatrecipesforme.com
6. The DNS server responds with the new IP address
7. The browser initiates an HTTP request to the new IP address <br>

A senior analyst confirms that the website was compromised. The analyst checks the source code for the website. They notice that javascript code had been added to prompt website visitors to download an executable file. Analysis of the downloaded file found a script that redirects the visitors’ browsers from yummyrecipesforme.com to greatrecipesforme.com. 
The cybersecurity team reports that the web server was impacted by a brute force attack. The disgruntled baker was able to guess the password easily because the admin password was still set to the default password. Additionally, there were no controls in place to prevent a brute force attack. 
Your job is to document the incident in detail, including identifying the network protocols used to establish the connection between the user and the website.  You should also recommend a security action to take to prevent brute force attacks in the future.


# Incident Report: Brute Force Attack and Website Compromise - YummyRecipesForMe.com

## 📌 Summary

On February 10,2025, YummyRecipesForMe.com was compromised through a **brute force attack** targeting the web host's administrative login. The attacker successfully guessed a default password and injected malicious JavaScript code into the website's source. The code prompted visitors to download and run a file, which led to a redirection to a fraudulent website, GreatRecipesForMe.com, where proprietary recipes were made publicly accessible. Multiple customers reported suspicious behavior and performance issues on their personal computers.

---

## 🧪 Investigation Findings

1. **Initial Access Vector:**
   - A disgruntled individual executed a **brute force attack** using a list of known default passwords.
   - Gained unauthorized access to the admin panel using the default credentials.

2. **Malicious Activity:**
   - Modified the website’s source code by embedding JavaScript.
   - Script prompted users to download a file disguised as a browser update.
   - The executable redirected users to `greatrecipesforme.com`, a spoofed version of the original site.

3. **Customer Impact:**
   - Several customers reported the website prompting a download and redirection.
   - Performance issues were noted after executing the downloaded file, suggesting malware infection.

4. **Technical Observation in Sandbox:**
   - DNS resolution for `yummyrecipesforme.com` returns the correct IP.
   - HTTP request initiated and the malicious executable is downloaded.
   - Second DNS resolution occurs for `greatrecipesforme.com`.
   - Browser is redirected to the malicious site.

---

## 🌐 Network Protocols Involved

- **DNS (Domain Name System):**
  - Used to resolve domain names to IP addresses.
  - Observed for both `yummyrecipesforme.com` and `greatrecipesforme.com`.

- **HTTP (Hypertext Transfer Protocol):**
  - Used to request and receive web content from both sites.
  - Also used to download the malicious executable file.

---

## 🧠 Root Cause

- Administrative account was protected with a **default password**.
- **No rate limiting** or **account lockout** mechanisms were in place to prevent brute force attacks.
- Lack of logging and alerting allowed the attack to go undetected until customer complaints emerged.

---

## 🛡️ Recommendations

1. **Enforce Strong Password Policies:**
   - Replace default passwords with complex, unique credentials.

2. **Implement Brute Force Mitigations:**
   - Account lockout after multiple failed attempts.
   - Use CAPTCHA on login pages.
   - Rate limiting on authentication endpoints.

3. **Enable Two-Factor Authentication (2FA):**
   - Add an extra layer of security for all admin-level logins.

4. **Conduct Regular Security Audits:**
   - Regularly review web server and CMS configurations.
   - Scan for unauthorized code changes or uploads.

5. **Web Application Firewall (WAF):**
   - Deploy a WAF to block malicious traffic and detect abnormal login behavior.

6. **Monitor and Alert:**
   - Implement logging and real-time alerts for failed login attempts and source code changes.

7. **Malware Scanning:**
   - Automatically scan uploaded or downloaded files to detect and block malicious code.

---

## ✅ Resolution Status

> The web server is currently under forensic analysis.  
> Admin access has been locked and credentials reset.  
> Malicious code has been removed from the source.  
> DNS records and HTTP requests have been logged for legal and investigatory purposes.  
> Security recommendations are being implemented to prevent future attacks.

---

## 📁 Report By

- **Analyst:** Pascal Egbenda
- **Date:** February 2025
- **Tools Used:** tcpdump, DNS logs, HTTP logs, Source code review  
