# 🌐 Internet Standards Measurement Project – DC-IS3C (Dynamic Coalition on Internet Standards, Security and Safety)

This repository is part of the **Dynamic Coalition on Internet Standards, Security and Safety (DC-IS3C)** within the **Internet Standards, Security and Safety Coalition (IS3C)** under the **Internet Governance Forum (IGF)**.  

It provides an **open-source, verifiable measurement platform** to evaluate the **adoption and deployment of Internet security, trust, and interoperability standards** globally, created by a group of experts in the technical community of **Latin America and Caribbean (LAC)** region.

The project includes:
- A **web interface** (`index.html`) that provides an interactive measurement dashboard.
- A **Node.js backend server** that performs technical checks on domains and returns structured JSON responses.

---

## 🚀 Quick Start

### 1️⃣ Install and Run Locally

```bash
npm install
npm start
By default, the server listens on port 4000.

Then, open index.html in your browser to use the measurement interface.

The web client consumes the backend endpoints below to run all tests dynamically.

🧩 Measurement Endpoints
Each endpoint returns a JSON object containing results and diagnostic information.

📧 Email and Messaging Security
Endpoint	Description
GET /mx/:domain	Retrieves MX (Mail Exchanger) records.
GET /smtputf8/:domain	Checks if mail servers support SMTPUTF8 (RFC 6531) on ports 25 and 587.
GET /dkim/:domain?selector=default	Detects DKIM records for the given selector.
GET /emailconfig/:domain	Detects SPF, DMARC, DKIM, and MX configurations.

🌐 DNS and Security Infrastructure
Endpoint	Description
GET /dnsrecords/:domain	Returns all DNS records (A, AAAA, MX, NS, TXT, CNAME).
GET /dnsserver/:domain	Lists authoritative name servers (NS).
GET /dnssec/:domain	Checks DNSSEC presence (DS/DNSKEY) using Google DNS.
GET /dnssecurity/:domain	Verifies DNSSEC using DoH (Google, Cloudflare).
GET /caa/:domain	Retrieves CAA (Certificate Authority Authorization) records.
GET /tlsa/:domain	Checks for TLSA (DANE) records under _443._tcp.domain.
GET /rpki/:domain	Validates IP prefixes via RIPE Stat and Cloudflare RPKI Validator.
GET /txtrecords/:domain	Returns all TXT DNS records.

🔐 TLS and Certificate Validation
Endpoint	Description
GET /tlsinfo/:domain	Returns TLS version, cipher suite, OCSP, and key info.
GET /sslchain/:domain	Extracts the full certificate chain with issuer and validity data.
GET /tlsciphers/:domain	Lists supported ciphers for TLSv1.2 and TLSv1.3.
GET /tlsconfig/:domain	Fetches TLS configuration results from Mozilla TLS Observatory.
GET /tlssimulation/:domain	Simulates TLS handshakes for modern and legacy browsers.
GET /tlsa/:domain	Lists DANE/TLSA records.

🧱 Web and Application Security
Endpoint	Description
GET /headers/:domain	Lists HTTP response headers and security attributes (HSTS, CSP, etc.).
GET /httpsecurity/:domain	Summarizes main security headers (HSTS, CSP, Referrer-Policy, etc.).
GET /securitytxt/:domain	Checks for .well-known/security.txt presence.
GET /cookies/:domain	Lists cookies returned by the website.
GET /firewall/:domain	Detects Web Application Firewalls (Cloudflare, Sucuri, Akamai, ModSecurity).
GET /sitefeatures/:domain	Detects site features like forms, login, analytics, search, video, ecommerce.
GET /techstack/:domain	Identifies technologies (WordPress, React, Vue, Angular, etc.).
GET /w3c/:domain	Runs HTML validation via W3C Validator API.
GET /quality/:domain	Fetches performance, accessibility, SEO metrics from Google PageSpeed API.
GET /carbon/:domain	Estimates environmental footprint via WebsiteCarbon API.
GET /crawlrules/:domain	Retrieves and parses robots.txt.
GET /listedpages/:domain	Extracts URLs from sitemap.xml.
GET /linkedpages/:domain	Lists internal and external links from the homepage.
GET /socialtags/:domain	Extracts meta and OpenGraph social tags.
GET /archive/:domain	Retrieves snapshots from the Internet Archive (Wayback Machine).

🛰️ Network and Hosting Diagnostics
Endpoint	Description
GET /ipinfo/:domain	Resolves IPv4 and IPv6 addresses with geolocation, ASN, and ISP info.
GET /serverinfo/:domain	Combines IP, ASN, organization, ISP, and country.
GET /serverlocation/:domain	Returns geographic coordinates and timezone.
GET /serverstatus/:domain	Checks HTTP/HTTPS reachability and redirect status.
GET /openports/:domain	Scans standard ports (21, 22, 25, 53, 80, 110, 143, 443, 465, 587, 993, 995, 8080).
GET /traceroute/:domain	Displays traceroute hops via HackerTarget API.
GET /associatedhosts/:domain	Lists related hosts/subdomains sharing the same IP.
GET /redirectchain/:domain	Follows and lists HTTP redirects.
GET /screenshot/:domain	Returns screenshot URL via thum.io API.

🏷️ Domain Registration and Reputation
Endpoint	Description
GET /whois/:domain	Extracts WHOIS data (organization, country).
GET /domaininfo/:domain	Retrieves RDAP info, registry name, status, creation, and expiration.
GET /ranking/:domain	Returns Tranco global ranking position.
GET /block/:domain	Tests DNS blocking via Google, Cloudflare, and Quad9 resolvers.
GET /malware/:domain	Queries URLHaus for known malware activity.

🧮 Additional Analysis and Security Intelligence
Endpoint	Description
GET /dnssecurity/:domain	Cross-validates DNSSEC results from different DoH resolvers.
GET /carbon/:domain	Evaluates sustainability impact and CO₂ emissions.
GET /tlssimulation/:domain	Tests client compatibility with TLS 1.2/1.3.
GET /archive/:domain	Provides archived versions of websites.
GET /block/:domain	Detects filtering or censorship by DNS resolvers.
GET /malware/:domain	Lists known malicious URLs.
GET /traceroute/:domain	Reports hop-by-hop routing paths.

🧠 Technical Overview
Built entirely with native Node.js modules (http, https, dns, net, tls, url).

No third-party dependencies required.

Handles timeouts, network errors, and provides normalized JSON output.

Includes in-memory caching for DNS/HTTP responses to optimize repeated queries.

Public APIs integrated:

Google DNS, Cloudflare DNS, RIPE Stat, Mozilla TLS Observatory

WebsiteCarbon, HackerTarget, Tranco, URLHaus, Internet Archive

Adds CORS headers (Access-Control-Allow-Origin: *) for browser clients.

🧭 Project Goals
Measure adoption of Internet security and trust standards: DNSSEC, RPKI, TLS, SMTPUTF8, SPF, DMARC, etc.

Provide reproducible data for DC-IS3C research and capacity-building efforts.

Support open collaboration for Internet measurement, transparency, and security awareness.

Offer an extensible platform for regional and global Internet standard compliance dashboards.

📈 Future Roadmap
Data aggregation and storage for time-series measurements.

Interactive visualization dashboards.

Scoring and compliance ranking for key standards.

Integration with IS3C global observatory and other DC-IS3C tools.

Automated scheduled scans and periodic open reports.

🧾 License
Released under the MIT License for transparency, reuse, and collaboration in alignment with the IS3C mission.

Maintained by:
Dynamic Coalition on Internet Standards, Security and Safety (DC-IS3C)
Internet Standards, Security and Safety Coalition (IS3C)
Internet Governance Forum (IGF)
