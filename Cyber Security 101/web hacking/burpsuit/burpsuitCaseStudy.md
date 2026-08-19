

Title: Burp Suite Basics — Summary Report
 
##  Problem
 
  The objective was to learn and validate basic Burp Suite proxy workflows: launch Burp Suite Community Edition, configure a browser to route traffic through Burp (using FoxyProxy or Burp's built-in browser), intercept and modify HTTP requests, populate the Target site map, set an appropriate scope to limit captured traffic, import the PortSwigger CA to inspect HTTPS, and perform a simple reflected XSS test via intercepted form data.
    
## What I investigated
    

- Starting Burp Suite Community and reaching the main interface (Dashboard, Proxy, Target).
- Burp Settings to understand User vs Project scope and locate options such as Sessions, Updates, Hotkeys, and Client TLS Certificates.
- 
![](../../assets/Pasted%20image%2020260819215443.png)

- Browser proxy configuration using FoxyProxy (127.0.0.1:8080) and verifying traffic appears in Burp Proxy.
- Adding the target (http://MACHINE_IP/) to Burp Target scope and enabling Proxy interception only when URL is in scope.
- Downloading and importing the Burp CA from http://burp/cert into Firefox and trusting it for website identification to avoid TLS warnings.
- Using the Target site map to discover endpoints and locating an unusual endpoint mentioned by the room tasks.

![](../../assets/Pasted%20image%2020260819215238.png)
-
- Intercepting a POST to the support form (/ticket), URL-encoding an XSS payload, and forwarding the modified request to observe reflected client-side execution.

 What I found

- Burp Suite Community launches into a main interface where Proxy and Target tabs are accessible after clicking Start Burp.
- Some settings live under User options while others are Project options — toggling the Type filter in Settings clarifies persistence (note: Community Edition does not persist project settings between sessions).
- Proper FoxyProxy config (127.0.0.1:8080) plus turning Intercept on in Burp results in the browser’s requests appearing in Burp Proxy; common misconfigurations are wrong IP/port or leaving Intercept off.
- Adding the application host to Target scope and enabling the Proxy condition “URL is in target scope” prevents unrelated traffic from cluttering Proxy and Site map.
- Importing the PortSwigger CA and marking it trusted for website identification lets Burp intercept HTTPS without browser warnings; forgetting the trust checkbox causes persistent TLS warnings.
- The Site map populated by browsing revealed additional endpoints (including the unusual endpoint the lab referenced), making enumeration straightforward.
- By intercepting the POST to /ticket and replacing the email field with a URL-encoded XSS payload (then forwarding), I triggered the reflected XSS as demonstrated in the lab — showing how request manipulation via Proxy can validate input-handling weaknesses.

![](../../assets/Pasted%20image%2020260819215348.png)

![](../../assets/Pasted%20image%2020260819215412.png)



## What I learned

- Workflow: Launch Burp → configure browser proxy → confirm interception → add target to scope → import CA for HTTPS → use Proxy and Site map to enumerate → modify requests to test vulnerabilities.
- Scope management is essential to keep Proxy history and Site map relevant and readable during testing.
- Browser trust of the Burp CA is required for inspecting HTTPS traffic and avoiding misleading browser warnings.
- Intercepting and editing requests (and remembering to URL-encode when needed) is a practical method to test input validation and discover reflected XSS and other injection issues.
- Burp’s built-in tools (Proxy, Repeater, Site map) provide a repeatable, auditable workflow for manual testing; practice increases speed and confidence.

Conclusion Completing these steps provides a solid foundation for manual web application testing with Burp Suite. The next practical steps are to practice repeated request modification in Repeater, automate payload variations with Intruder (where available), and reinforce scope and CA management in additional labs.