# Common Network Security Threats

## 1. Introduction

Network security is essential for protecting computers, servers, applications, and data from unauthorized access, disruption, and misuse. As organizations increasingly depend on interconnected networks and online services, attackers can exploit network weaknesses to steal information, interrupt services, impersonate legitimate systems, or manipulate network communication. Common threats such as DoS/DDoS attacks, Man-in-the-Middle attacks, IP spoofing, and DNS poisoning can affect individuals, businesses, and critical infrastructure. Understanding how these attacks work, their real-world impact, and the appropriate mitigation techniques helps network administrators build stronger and more secure networks.

---

## 2. DoS/DDoS Attacks

### How They Work

A Denial-of-Service (DoS) attack attempts to make a computer system, server, or network service unavailable to legitimate users by overwhelming it with a large number of requests or consuming its available resources. A Distributed Denial-of-Service (DDoS) attack uses multiple compromised devices, often called a botnet, to generate traffic or requests simultaneously. Because the traffic comes from many different sources, DDoS attacks can be more difficult to block than attacks from a single system.

### Real-World Example

A well-known example is the **2016 Mirai botnet attack against Dyn**, a major DNS infrastructure provider. Mirai compromised vulnerable Internet of Things (IoT) devices and used them as a botnet to generate a large-scale DDoS attack. The attack disrupted access to several major websites and online services.

### Impact

DoS/DDoS attacks can cause service downtime, slow network performance, financial losses, loss of customer trust, and disruption of critical online services. For organizations that depend heavily on online availability, prolonged attacks can significantly affect business operations.

### Mitigation Strategies

1. **Traffic filtering and rate limiting:** Network devices and security systems can detect and limit unusually high volumes of traffic or requests.

2. **DDoS protection services:** Organizations can use specialized DDoS mitigation services and content delivery networks (CDNs) to absorb and filter malicious traffic.

3. **Network monitoring and alerting:** Continuous monitoring can help administrators detect unusual traffic patterns early and respond before the attack causes major disruption.

---

## 3. Man-in-the-Middle (MITM) Attacks

### How They Work

A Man-in-the-Middle (MITM) attack occurs when an attacker secretly intercepts communication between two parties. The attacker may monitor, capture, or modify the information being exchanged while making the communicating parties believe that they are communicating directly with each other. MITM attacks can occur through techniques such as malicious Wi-Fi networks, session hijacking, or exploitation of weak encryption.

### Real-World Example

A significant real-world example was the **Superfish incident involving Lenovo laptops in 2015**. Superfish software was pre-installed on some Lenovo consumer laptops and installed a self-signed root certificate that allowed the software to intercept HTTPS communications. This created a Man-in-the-Middle security risk because encrypted web traffic could be intercepted and inspected by the software.

### Impact

MITM attacks can result in the theft of login credentials, session information, personal data, or other sensitive information. Attackers may also modify communication, potentially causing financial or operational damage. In the Superfish incident, the weakened certificate trust model exposed users to serious security risks.

### Mitigation Strategies

1. **Use strong encryption:** HTTPS and TLS should be used to protect data transmitted between systems.

2. **Avoid untrusted networks:** Users should avoid connecting to unknown or suspicious Wi-Fi networks and use a trusted VPN when appropriate.

3. **Use secure authentication:** Multi-factor authentication (MFA) can reduce the impact of stolen credentials.

---

## 4. IP Spoofing

### How It Works

IP spoofing is a technique in which an attacker modifies the source IP address of network packets so that they appear to come from a different, trusted, or legitimate system. This can be used to hide the attacker's actual identity or to impersonate another system.

IP spoofing is commonly associated with DDoS attacks, particularly reflection and amplification attacks. In such attacks, forged source IP addresses can make responses from third-party systems reach the victim instead of the attacker.

### Real-World Example

A documented example of IP spoofing occurred during **large-scale memcached-based DDoS attacks in 2018**. Attackers used spoofed source IP addresses to make vulnerable memcached servers send large responses toward their intended victims. GitHub was targeted by a record-scale memcached amplification attack that reached approximately 1.35 Tbps.

### Impact

IP spoofing can be used to bypass IP-based access controls, hide the source of malicious traffic, and support attacks such as DDoS. It can also make incident investigation more difficult because the apparent source address may not belong to the actual attacker.

### Mitigation Strategies

1. **Ingress filtering:** Network administrators and Internet service providers can filter incoming packets with invalid or unexpected source addresses.

2. **Egress filtering:** Outgoing traffic can also be checked to prevent systems within a network from sending packets with forged source addresses.

3. **Use strong authentication:** Organizations should not rely only on source IP addresses for authentication or access control. Additional authentication mechanisms should be used.

---

## 5. DNS Poisoning / DNS Spoofing

### How It Works

DNS poisoning, also called DNS cache poisoning, is an attack in which false DNS information is introduced into a DNS resolver's cache. DNS normally translates domain names, such as a website address, into IP addresses. In a DNS poisoning attack, the attacker causes a domain name to resolve to an incorrect or malicious IP address, potentially redirecting users to a fraudulent website.

### Real-World Example

A major example was the **2008 DNS cache-poisoning vulnerability discovered by security researcher Dan Kaminsky**. The vulnerability could allow attackers to inject false DNS information into DNS caches and redirect users to malicious destinations. The discovery led major technology and DNS organizations to coordinate a global security update to reduce the risk.

### Impact

DNS poisoning can redirect users to phishing websites, expose login credentials, distribute malware, or interrupt access to legitimate services. It can also damage trust in online services because users may unknowingly interact with a malicious destination.

### Mitigation Strategies

1. **Use DNSSEC:** DNS Security Extensions (DNSSEC) provide mechanisms for validating the authenticity and integrity of DNS responses.

2. **Secure DNS infrastructure:** Keep DNS servers updated, properly configured, and protected from unauthorized access.

3. **Use trusted DNS resolvers and monitoring:** Organizations should use reputable DNS services and monitor DNS activity for unexpected changes or suspicious responses.

---

## 6. Comparison of Network Security Threats

| Attack                 | Attack Vector                                        | Who Is at Risk?                                   | Difficulty to Execute | Ease of Mitigation |
| ---------------------- | ---------------------------------------------------- | ------------------------------------------------- | --------------------- | ------------------ |
| DoS/DDoS               | Flooding a target with excessive traffic or requests | Websites, servers, organizations, online services | Medium to High        | Medium             |
| MITM                   | Intercepting communication between two parties       | Users, organizations, public Wi-Fi users          | Medium                | Medium             |
| IP Spoofing            | Forging the source IP address of network packets     | Networks, servers, online services                | Medium                | Medium             |
| DNS Poisoning/Spoofing | Manipulating DNS information to redirect users       | Website users, organizations, DNS infrastructure  | Medium to High        | Medium             |

---

## 7. Conclusion

The study of common network security threats highlights the importance of protecting network infrastructure and communication systems. DoS/DDoS, MITM, IP spoofing, and DNS poisoning can affect the availability, confidentiality, integrity, and trustworthiness of network services.

The key takeaways for a network administrator are:

1. **Monitor network activity continuously:** Regular monitoring helps detect unusual traffic, suspicious connections, DNS changes, and possible attacks at an early stage.

2. **Apply multiple layers of security:** Firewalls, encryption, secure authentication, DNS security, traffic filtering, and access controls should be used together rather than relying on a single security mechanism.

3. **Keep systems secure and updated:** Regular software updates, secure configurations, strong authentication, and proper security policies can significantly reduce the risk of network attacks.

---

## 8. References

1. National Institute of Standards and Technology (NIST) — Cybersecurity Framework and Network Security Guidance.

2. Cybersecurity and Infrastructure Security Agency (CISA) — Guidance on Distributed Denial-of-Service Attacks and Cybersecurity.

3. MITRE ATT&CK — Enterprise Techniques and Network Attack Techniques.

4. Federal Trade Commission (FTC) — Lessons from the Lenovo Superfish Man-in-the-Middle Security Incident.

5. Lenovo Security Advisory — Superfish Vulnerability and Potential Man-in-the-Middle Attack.

6. Cloudflare — IP Spoofing and DDoS Attack Analysis.

7. Wired — Dan Kaminsky and the 2008 DNS Cache-Poisoning Vulnerability.

8. SANS Institute — Network Security and Common Network Attack Techniques.
