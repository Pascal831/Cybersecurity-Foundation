# Cybersecurity Incident Report: Analyze Network Attacks
> Network attacks.

> Please visit this [link](https://www.coursera.org/learn/networks-and-network-security?specialization=google-cybersecurity) for further information. 

## Scenario

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. 

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor. 

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.



# Incident Report: SYN Flood Attack on Travel Agency Web Server

## 📌 Summary

On Feb xx, an automated alert from the monitoring system indicated a potential problem with the company’s web server. Attempts to access the site resulted in **connection timeout errors**. A packet analysis confirmed that the server was being targeted by a **SYN flood attack**, overwhelming its ability to respond to legitimate user requests.

---

## 🧪 Investigation Steps

1. **Alert Received:**
   - Monitoring system triggered an alert indicating unusual traffic targeting the web server.

2. **Symptom Observation:**
   - Employees and customers were unable to access the website.
   - Error observed: _Connection Timed Out_.

3. **Packet Capture Analysis:**
   - A packet sniffer was used to capture and inspect network traffic.
   - Discovered a **large number of TCP SYN packets** originating from an unfamiliar IP address.
   - The volume of SYN packets exceeded normal traffic patterns, indicating a **Denial-of-Service (DoS)** attempt.

4. **Immediate Action Taken:**
   - The web server was taken offline temporarily to prevent further resource exhaustion.
   - The offending IP address was **blocked at the firewall** to halt ongoing traffic from the attacker.

---

## 🧠 Root Cause

The root cause of the outage was a **SYN Flood Attack**, a form of **TCP-based DoS attack** where a malicious actor sends a high volume of TCP SYN requests to exhaust server resources.

- The server allocates memory and resources for each incomplete TCP handshake.
- Due to the flood of requests, legitimate connections could not be established.
- Resulted in **service unavailability** for internal users and external customers.

---

## 🌐 Type of Attack

- **Attack Name:** SYN Flood
- **Attack Vector:** TCP (Transmission Control Protocol)
- **Category:** Denial-of-Service (DoS)
- **Impact:** Website unavailability, business disruption

---

## 🛡️ Recommendations

1. **Implement SYN Cookies:**
   - Enable SYN cookies on the web server to handle excessive SYN requests without allocating memory until the handshake completes.

2. **Rate Limiting and Connection Throttling:**
   - Apply rate-limiting rules for inbound SYN traffic to detect and control abnormal bursts.

3. **Deploy a Web Application Firewall (WAF):**
   - Use a WAF to provide additional protection against common network-based attacks.

4. **Consider a DDoS Protection Service:**
   - Leverage services like Cloudflare, AWS Shield, or Azure DDoS Protection to mitigate large-scale SYN floods.

5. **Network Intrusion Detection System (NIDS):**
   - Deploy IDS/IPS tools like Snort or Suricata to detect anomalies and automate blocking.

---

## ✅ Resolution Status

> The server was restored after a temporary shutdown.  
> The IP address was blocked, and access to the website has resumed for internal users.  
> Further mitigation strategies are being reviewed for long-term defense.

---

## 📁 Report By

- **Analyst:** Pascal Egbenda  
- **Date:** February 2025 
- **Tool(s) Used:** Packet sniffer (e.g., tcpdump/Wireshark), firewall logs, monitoring system  
