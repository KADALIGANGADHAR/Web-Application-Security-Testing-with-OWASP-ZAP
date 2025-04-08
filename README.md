# Web-Application-Security-Testing-with-OWASP-ZAP

## 1.Introduction
**OWASP ZAP (Zed Attack Proxy) is an open-source web application security scanner used to identify vulnerabilities in web applications. It is widely used by security professionals and ethical hackers for manual and automated penetration testing.**

## 2.Prerequisites
**•	Operating System: Kali Linux (or any OS with OWASP ZAP installed)**

**•	Tools Required:**

**o	OWASP ZAP**

**o	DVWA (Damn Vulnerable Web Application) or Juice Shop**

**o	Firefox/Chrome with Proxy settings configured**

## 3.Setting Up the Testing Environment**

> ## Step 1: Install OWASP ZAP
**•	Install OWASP ZAP from the official website or run it in Kali Linux using:zaproxy**
![image](https://github.com/user-attachments/assets/805f0e84-eda5-4d08-bbed-694aaef3c8e9)
![image](https://github.com/user-attachments/assets/9666bc80-ec97-4950-a6e2-002450555633)
![image](https://github.com/user-attachments/assets/2c0c7b55-f30e-4e70-80a6-7efc429f1631)
![image](https://github.com/user-attachments/assets/e1d233bf-0b23-4e05-9475-0c2857ba436a)
> ## Step 2: Configure Browser to Use ZAP Proxy
 - **To intercept traffic, configure your browser to route requests through ZAP.**

**1️.Find ZAP Proxy Address
Open ZAP → Tools → Options → Local Servers/Proxies.** 
![image](https://github.com/user-attachments/assets/1e52eef4-08ec-41c0-9d69-59010b281308)
**•	Default settings: Address: 127.0.0.1 or localhost  Port: 8080**
![image](https://github.com/user-attachments/assets/be58a901-3c67-4eba-86ea-1a127676d8db)
**2️.Install FoxyProxy Extension**

- **Open Firefox.**

- **Go to the FoxyProxy Standard extension page:FoxyProxy for Firefox**
![image](https://github.com/user-attachments/assets/e48eef92-fac5-4b29-a66d-255c54f59dd5)
- **Click "Add to Firefox" → "Add" when prompted.**
![image](https://github.com/user-attachments/assets/95ae97ca-a479-4707-807e-22b5174374a7)
- **Once installed, the FoxyProxy icon will appear in the Firefox toolbar.** 
![image](https://github.com/user-attachments/assets/4ca1aa7f-8e91-471d-8add-77a4ecbda095)
> ## Step 3: Configure a Proxy in FoxyProxy
- **Click the FoxyProxy icon in the toolbar.**

- **Select "Options" to open the configuration page.**

- **Click "Add New Proxy".**
![image](https://github.com/user-attachments/assets/e7876f96-cfd7-4802-980f-d215511ba2e6)
 - **Under the General tab:**
   
   **o	Give it a name (e.g., "My Proxy").**

   **o	Enable "Enabled" checkbox.**

 - **Under the Proxy Details tab:**
   
   **o	Choose the proxy type (HTTP, HTTPS, SOCKS4, or SOCKS5).**

   **o	Enter the Proxy IP address and Port.**

   **o	If required, enter Username & Password under the Authentication section.**
- **Click Save.**
![image](https://github.com/user-attachments/assets/035fb5b5-bdfc-444d-871d-3f3bc619f8b2)
> ## Step 4: Enable the Proxy
- **Click the FoxyProxy icon in the toolbar.**
  
- **Select the newly added proxy profile from the list.**
  
- **If you want to disable the proxy, choose "Disable FoxyProxy".**
________________________________________
> ## Step 5: Test the Proxy
- **Open a new tab and visit https://www.whatismyip.com/**
  
- **If the proxy is working, it will show the proxy’s IP address instead of your actual IP.**

- **Verify Proxy is Working**

- **Open a website (e.g., http://dvwa.local). or its Ip address**
![image](https://github.com/user-attachments/assets/d52a8cb6-fb0c-4afc-8c2b-5eb671ba368f)
- **Check if requests appear in ZAP under "Sites".**
![image](https://github.com/user-attachments/assets/823b4a4f-0964-42b8-b90d-104333829cac)
## 4.Passive Scanning (Non-Intrusive Analysis)
 **1.	Open DVWA (http://dvwa.local)or with IP and log in (admin / password).**
 **2.	Browse different pages while ZAP passively scans for vulnerabilities.**
 **3.	View results in the Alerts tab for security issues like:**
- **Content security policy**
- **Cross domain misconfiguration**
- **Missing anti-clickjacking Header**
- **Server leaks information**
![image](https://github.com/user-attachments/assets/9d9df7de-d667-4a05-b6f8-be4761f79ddf)
## 5.Active Scanning (Automated Attack Simulation)
 **1.	In ZAP, right-click on DVWA URL or IP address → Attack → Active Scan.**
 **2.	Select DVWA as the target.**
 **3.	Click Start Scan.**
![image](https://github.com/user-attachments/assets/3eda5356-2109-49c4-886d-83844a7bf1b4)
![image](https://github.com/user-attachments/assets/5094fa0d-5800-4858-a749-6e0c5947db90)
![image](https://github.com/user-attachments/assets/15afa48d-e33d-488c-ba7e-8bb797d7d236)
![image](https://github.com/user-attachments/assets/fbdb9a8d-7ead-4223-8af5-1f18e7f7b147)
 **4. Vulnerabilities detected:** 
 
- **SQL Injection.**
   
- **Cross-Site Scripting (XSS).**
   
- **Server side code injection and some more.**
![image](https://github.com/user-attachments/assets/f2d4ee08-3f94-4e73-83c6-d326bda509b3)
- **For Checking Vulnerabilities  go to alerts or progress.**
![image](https://github.com/user-attachments/assets/287510fd-75e2-450a-97f0-96bae71414a5)
- **Click on progress Icon for progress.**
![image](https://github.com/user-attachments/assets/f932a42e-6596-4316-a847-bc7f5a0d50f9)
![image](https://github.com/user-attachments/assets/7a24f213-67ef-47bc-ba47-0010ed0f7862)
![image](https://github.com/user-attachments/assets/ab8393fd-c910-41c1-baab-20168c341faf)
## 6.Manual Testing (Exploiting Vulnerabilities)
**Step 1: SQL Injection (SQLi) Testing in DVWA**

**Scenario: Finding SQL Injection Vulnerability**

**1️. Open DVWA in a browser and log in.**

**2️. Navigate to "SQL Injection" from the left menu.**

**3️. You will see an input field asking for a User ID.**

**4️. Start with a simple SQLi payload:``' OR 1=1 --``** 
![image](https://github.com/user-attachments/assets/9854d29b-fa1c-4f3a-8f11-6007bd86c6ff)
![image](https://github.com/user-attachments/assets/389a8087-1214-41ab-98a8-75c27f4398f1)
**🔹 If successful, it should return all user details instead of one.**
**5️.Try extracting the database version:``' UNION SELECT NULL, @@version --``**  
![image](https://github.com/user-attachments/assets/b692d968-9894-4a89-b408-8db180191ec3)
![image](https://github.com/user-attachments/assets/9a3c5932-e14a-4de7-bf69-d2daf078d06a)
**🔹 If the database version is displayed, SQLi is possible.**
**6️.Try getting all tables:``' UNION SELECT table_name, NULL FROM information_schema.tables --``** 
![image](https://github.com/user-attachments/assets/f5b3abbe-e090-4eb6-8a73-bc30d5590f3c)
![image](https://github.com/user-attachments/assets/64a7eb03-e9b7-4904-bd67-20f2d704614f)
**🔹 This should list database tables.**
**Step 2: XSS Testing in DVWA**
 **Scenario: Testing Reflected XSS**
 
**1️. Navigate to "XSS Reflected" in DVWA.**

**2️. There will be a text input field (e.g., "What’s your name?").**

**3️. Enter this basic XSS payload:``<script>alert('XSS')</script>``**
![image](https://github.com/user-attachments/assets/89cc0909-1926-4540-a2f4-7e4313423c1b)
![image](https://github.com/user-attachments/assets/6130bdf7-9982-407b-bcc7-f6f2237ad25a)

**🔹 If an alert box appears, the site is vulnerable to XSS.**

**4️. Try bypassing filters with encoded payloads:``<img src=x onerror=alert('XSS')>``**
![image](https://github.com/user-attachments/assets/afd38f0e-2adf-43f8-b5c7-f9e144246679)
![image](https://github.com/user-attachments/assets/1447155c-dc40-407a-a421-018b0978c8ab)
![image](https://github.com/user-attachments/assets/3957ad8b-3c18-49cf-937f-2e8865057199)
**🔹 This injects a script using an image error event.**

**Step 3: Automating XSS & SQLi Testing with OWASP ZAP**

- **Intercept & Scan DVWA Using ZAP**
  
- **Start Browsing DVWA Through ZAP.**
  
- **Click "Sites" in ZAP and find DVWA.**

- **Right-click on the site and select "Spider this site".**
![image](https://github.com/user-attachments/assets/e530fa95-27a5-4edb-991b-06e2d4fa0185)
![image](https://github.com/user-attachments/assets/92c86988-cff2-4bf1-97ae-61133328b3ef)
- **Run an Active Scan to find vulnerabilities.**
![image](https://github.com/user-attachments/assets/209c46e9-dfb6-431a-8aaa-945725348d55)
![image](https://github.com/user-attachments/assets/38ee1e54-52d9-4d1f-8046-d173accddc82)
- **Analyze results in the Alerts tab.**

**Step 4: Fuzzing with ZAP**

- **Brute-Forcing Input Fields.**
![image](https://github.com/user-attachments/assets/6b04fec5-4127-4a54-8b23-53824b0de1b7)
**1️. In ZAP, navigate to "Request" > "Fuzzer".** 
![image](https://github.com/user-attachments/assets/2c987550-e227-4659-9856-5ee75d3fd2cd)
**2️. Select the username and password parameters in the login request.**
![image](https://github.com/user-attachments/assets/3fce758c-c673-49b1-b2d5-3d014e621776)
![image](https://github.com/user-attachments/assets/bf3f3d42-8ac7-4b39-8d2e-61e4f22e3bab)
![image](https://github.com/user-attachments/assets/7765cda0-7a00-4ffe-9422-6dad9335516f)
![image](https://github.com/user-attachments/assets/99f490e8-9230-43bd-ae41-67a8a3e580b0)
![image](https://github.com/user-attachments/assets/0f3f7a5e-5cd6-4e30-8ca2-37b8d8f690fd)
**3️. Add fuzzing payloads for testing authentication bypass:**
![image](https://github.com/user-attachments/assets/3bdf13ca-c52c-42a4-a097-6e06aeaef7af)
![image](https://github.com/user-attachments/assets/087e3522-1ef3-41a7-9a28-1a034f3fa8fe)
![image](https://github.com/user-attachments/assets/936cdf01-a22a-4ce7-9a65-4f903e62d3a7)
![image](https://github.com/user-attachments/assets/c0ed3029-5bee-4e7d-a020-964b872251f0)
![image](https://github.com/user-attachments/assets/5947f1d4-b916-452d-9ef3-1d747a0bdfab)
![image](https://github.com/user-attachments/assets/97971f02-2ba7-469d-a557-7346a03dc462)
## Conclusion

- **This project demonstrates a comprehensive approach to web application security testing using OWASP ZAP. By targeting intentionally vulnerable applications like DVWA, we explored a full testing workflow including passive scanning, active scanning, manual exploitation, and fuzzing techniques.**

- **Through this hands-on assessment, we were able to identify and exploit common vulnerabilities such as SQL Injection, Cross-Site Scripting (XSS), and security misconfigurations, mimicking real-world attack scenarios in a controlled environment.**

- **OWASP ZAP proved to be an essential tool for both automated and manual penetration testing, making it highly valuable for cybersecurity analysts, ethical hackers, and developers aiming to secure their applications.**



