# 🌐 How the Web Works
*Date: 2025-08-19*  
*Source: [HTTP Crash Course & Exploration](https://www.youtube.com/watch?v=iYM2zFP3Zn0)*; [How the web works](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works)

---

## 📌 Overview
General terms and ideas about how websites work. These notes include the definition for HTTP/HTTPS, DNS, TCP/IP, etc.

---

## 🔍 Key Concepts
- *TCP/IP*: Internet protocols used to define data handling on the internet
- *DNS*: System used to save information about a website
- *HTTP/HTTPS*: Protocols used for a website's responses

---

## 🧠 Notes
- *HTTP* stands for *Hyper Text Transfer Protocol*. It is used for the communication between web servers and clients -- this protocol is used for HTTP requests/responses.
- HTTP is stateless, which means that every request is *independant* and doesn't withold information about previous requests
- *HTTPS* stands for *Hyper Text Transfer Protocol Secure* -- it offers the same functions as HTTP, but ensuring that all data sent between the web server and its clients are encrypted with SSL/TLS certificates. These certificates are installed from the web host's side and are crucial for sensitive requests such as credit card transactions, login processes, etc
- The HTTP requests can come under multiple types of requests, but the main four would be:
    - *GET*: Retrieves data from the server
    - *POST*: Submit data to the server
    - *PUT*: Update data already on the server
    - *DELETE*: Deletes data from the server
- Along with the requests, these HTTP requests also come with their respective *Status Codes*, which follow this range:
    - *1XX*: Informational -- it means the request has been received or that it is under processing
    - *2XX*: Success -- it means the request has been successfully received, understood and accepted
    - *3XX*: Redirect -- this represents that further action must be taken and/or the client will be redirected
    - *4XX*: Client Error -- the request does not have what it needs in order to be completed
    - *5XX*: Server Error -- Server failed to fullfill an apparent valid request
- A few most common status codes would be:
    - *200*: OK
    - *201*: OK created
    - *301*: Moved to new URL
    - *304*: Not modified (cached version)
    - *400*: Bad request
    - *401*: Unauthorized
    - *404*: Not found
    - *500*: Internal server error
- The main version of such HTTP/HTTPS requests run under HTTP/1.1 version which is now being updated into its HTTP/2 version by including multiplexing. That is, responses can be sent with more data at the same time (such as styles.css and script.js files at the same time) -- this allows a major revision of HTTP, lower latency, response multiplexing along with a faster, more efficient and secure alternative
- Reverse engineering from the HTTP protocols, we have the *DNS* (Domain Name System) which acts as an address book for websites. When an URL is typed on your browser, it searches on the DNS to find its corresponding IP address for that website
- All of this information is communicated through the *TCP/IP* (Transmission Control Protocol and Internet Protocol) protocols, which define how data should travel across the internet

---

## ⚠️ Common Vulnerabilities / Risks
- *MITM (man-in-the-middle)*: Attacks where information is intercept and altered during HTTP traffic
- *XSS (Cross-Site Scripting)*: Injection of malicious scripts into web pages
- *SQLi (SQL Injection)*: Sending malicious SQL under HTTP requests to manipulate database information
- *Command Injection*: Executing shell/system commands via insecure input handling
- *CSRF (Cross-Site Request Forgery)*: Tricks authenticated users into making unwanted requests (e.g. form submission)
- And many more...

---

## ✅ Mitigation & Best Practices
- Use HTTPS instead of HTTP along with a *valid SSL/TLS* certificate
- Ensure all user inputs are validated and sanitized, using parameterized queries
- Use CSRF tokens
- Verify origin headers
- Use *SameSite* cookie attribute