<h1>Valkyri's Wallet Security Checklist for Web Extensions</h1>

<table>
  <tr>
    <th>Audit</th>
    <th>Issues</th>
    <th>Sub-Issues</th>
    <th>Details</th>
  </tr>


  <!-- ================================= -->
  <!-- 1. SUPPLY CHAIN INTEGRITY -->
  <!-- ================================= -->

  <tr>
    <td rowspan="4">Supply Chain Integrity</td>
    <td rowspan="2">Dependency Risk</td>
    <td>Dependency Confusion</td>
    <td>Registry spoofing / package impersonation</td>
  </tr>
  <tr>
    <td>Vulnerable Versions</td>
    <td>Outdated or unpatched libraries</td>
  </tr>

  <tr>
    <td>Artifact Security</td>
    <td>Build Artifact Integrity</td>
    <td>Compromised or tampered build output</td>
  </tr>

  <tr>
    <td>CI/CD Exposure</td>
    <td>Pipeline Weakness</td>
    <td>Token leaks, insecure steps</td>
  </tr>



  <!-- ================================= -->
  <!-- 2. HARDCODED SECRETS -->
  <!-- ================================= -->

  <tr>
    <td rowspan="2">Hardcoded Secrets</td>
    <td rowspan="2">Secret Exposure</td>
    <td>Plaintext Secrets</td>
    <td>API keys / secrets embedded in code</td>
  </tr>
  <tr>
    <td>Weak Storage</td>
    <td>Unencrypted env vars or exposed config</td>
  </tr>



  <!-- ================================= -->
  <!-- 3. PRIVATE KEY SECURITY -->
  <!-- ================================= -->

<tr>
  <td rowspan="8">Private Key Security</td>
  <td rowspan="8">Key Handling Weakness</td>

  <td>Plaintext Key Storage</td>
  <td>Keys stored unencrypted in files, localStorage, or configs</td>
</tr>

<tr>
  <td>Weak Encryption</td>
  <td>Use of weak, custom, or non-standard encryption algorithms</td>
</tr>

<tr>
  <td>In-Memory Exposure</td>
  <td>Keys retained in RAM or logs without secure zeroization</td>
</tr>

<tr>
  <td>Poor Key Lifecycle</td>
  <td>Low-entropy key generation, reuse, or improper rotation</td>
</tr>

<tr>
  <td>Key Extraction Attacks</td>
  <td>Exposure via browser/extension APIs, debug tools, or dev builds</td>
</tr>

<tr>
  <td>Improper Backup & Recovery</td>
  <td>Seed phrases or backups stored insecurely or exported without safeguards</td>
</tr>

<tr>
  <td>Hardware Isolation Failure</td>
  <td>Lack of secure enclave/HSM usage where required</td>
</tr>

<tr>
  <td>Side-Channel Leakage</td>
  <td>Key inference through timing, power, or observable UI behavior</td>
</tr>


  <!-- ================================= -->
  <!-- 4. ACCESS CONTROL -->
  <!-- ================================= -->

  <tr>
    <td rowspan="4">Access Control</td>
    <td rowspan="4">Authorization Failures</td>
    <td>IDOR</td>
    <td>Accessing objects without authorization checks</td>
  </tr>
  <tr>
    <td>Unauthorized Signing</td>
    <td>Silent or unintended message/tx signing</td>
  </tr>
  <tr>
    <td>Exposed APIs When Locked</td>
    <td>Extension/wallet surfaces available pre-auth</td>
  </tr>
  <tr>
    <td>No User Confirmation</td>
    <td>Sensitive actions performed without prompts</td>
  </tr>



  <!-- ================================= -->
  <!-- 5. WEB FRONTEND SECURITY -->
  <!-- ================================= -->

  <tr>
    <td rowspan="9">Web Frontend Security</td>
    <td rowspan="3">Cross-Site Scripting (XSS)</td>
    <td>DOM XSS</td>
    <td>Unsafe dynamic HTML rendering</td>
  </tr>
  <tr>
    <td>Stored XSS</td>
    <td>Malicious payloads persist & execute</td>
  </tr>
  <tr>
    <td>Reflected XSS</td>
    <td>Injection through request parameters</td>
  </tr>

  <tr>
    <td rowspan="2">Clickjacking</td>
    <td>Missing Frame Protection</td>
    <td>No X-Frame-Options / frame-ancestors</td>
  </tr>
  <tr>
    <td>Weak CSP</td>
    <td>Lack of restrictive Content Security Policy</td>
  </tr>

  <tr>
    <td rowspan="2">Deceptive UI/UX</td>
    <td>Misleading UI</td>
    <td>Ambiguous or manipulative screens</td>
  </tr>
  <tr>
    <td>Transaction Spoofing</td>
    <td>Fake or unclear transaction previews</td>
  </tr>

  <tr>
    <td rowspan="2">Clipboard Attacks</td>
    <td>Unauthorized Reads</td>
    <td>Clipboard sniffing without permission</td>
  </tr>
  <tr>
    <td>Unauthorized Writes</td>
    <td>Silent address/data replacement</td>
  </tr>



  <!-- ================================= -->
  <!-- 6. DENIAL OF SERVICE -->
  <!-- ================================= -->

  <tr>
    <td rowspan="2">Denial of Service</td>
    <td rowspan="2">DoS Weakness</td>
    <td>No Rate-Limiting</td>
    <td>Unlimited request spam</td>
  </tr>
  <tr>
    <td>Improper Input Parsing</td>
    <td>Malformed payload crashes</td>
  </tr>



  <!-- ================================= -->
  <!-- 7. DOMAIN & INFRASTRUCTURE -->
  <!-- ================================= -->

<tr>
  <td rowspan="8">Domain & Infrastructure</td>
  <td rowspan="8">Domain / Infra Weakness</td>

  <td>Subdomain Takeover</td>
  <td>Dangling DNS entries enabling hostile takeover</td>
</tr>

<tr>
  <td>DApp Spoofing</td>
  <td>Phishing via homograph or visually similar domains</td>
</tr>

<tr>
  <td>CORS Misconfiguration</td>
  <td>Overly permissive origin rules exposing sensitive data</td>
</tr>

<tr>
  <td>ENS Risks</td>
  <td>Manipulated, outdated, or misconfigured ENS records</td>
</tr>

<tr>
  <td>Handle Takeover</td>
  <td>Compromised or impersonated social identities</td>
</tr>

<tr>
  <td>TLS Misconfiguration</td>
  <td>Weak ciphersuites, outdated TLS versions, or missing HSTS</td>
</tr>

<tr>
  <td>DNS Security</td>
  <td>Lack of DNSSEC or vulnerable DNS resolver configuration</td>
</tr>

<tr>
  <td>Certificate Integrity</td>
  <td>Expired, unpinned, or misissued TLS certificates</td>
</tr>



  <!-- ================================= -->
  <!-- 8. SECURITY POLICIES -->
  <!-- ================================= -->

  <tr>
    <td rowspan="3">Security Policies</td>
    <td rowspan="3">Policy Weaknesses</td>
    <td>Auto-Lock</td>
    <td>Idle session timeout misconfigured</td>
  </tr>
  <tr>
    <td>Password Policy</td>
    <td>Weak password strength/hashing</td>
  </tr>
  <tr>
    <td>KYC</td>
    <td>Missing or inconsistent compliance handling</td>
  </tr>



  <!-- ================================= -->
  <!-- 9. MANIFEST CONFIGURATION -->
  <!-- ================================= -->

  <tr>
    <td rowspan="4">Manifest Configuration</td>
    <td rowspan="4">Manifest Issues</td>
    <td>Permission Misconfiguration</td>
    <td>Over-scoped permissions</td>
  </tr>
  <tr>
    <td>Metadata Misconfig</td>
    <td>Wrong origins / scripts</td>
  </tr>
  <tr>
    <td>Excessive Extension Privileges</td>
    <td>Unnecessary APIs requested</td>
  </tr>
  <tr>
    <td>Missing CSP</td>
    <td>No internal content restrictions</td>
  </tr>



  <!-- ================================= -->
  <!-- 10. RPC LAYER SECURITY -->
  <!-- ================================= -->

  <tr>
    <td rowspan="7">RPC Layer Security</td>
    <td rowspan="7">RPC Issues</td>
    <td>Open RPC Methods</td>
    <td>Public access to sensitive endpoints</td>
  </tr>
  <tr>
    <td>RPC Authentication</td>
    <td>Missing access tokens / auth</td>
  </tr>
  <tr>
    <td>Payload Validation</td>
    <td>No schema validation</td>
  </tr>
  <tr>
    <td>Rate Limiting</td>
    <td>No throttling</td>
  </tr>
  <tr>
    <td>Error Leakage</td>
    <td>Internal debug info exposed</td>
  </tr>
  <tr>
    <td>Provider Authenticity</td>
    <td>Untrusted RPC backend</td>
  </tr>
  <tr>
    <td>Transport Security</td>
    <td>No HTTPS/WSS or cert pinning</td>
  </tr>


  <!-- ================================= -->
  <!-- 11. TRANSFER SECURITY -->
  <!-- ================================= -->

  <tr>
    <td rowspan="3">Transfer Security</td>
    <td rowspan="3">Transfer Issues</td>
    <td>Silent Transfers</td>
    <td>No confirmation for value movement</td>
  </tr>
  <tr>
    <td>Signature security audit</td>
    <td>Validates signature safety through proper scoping, replay protection, EIP-712, and secure verification.</td>
  </tr>
  <tr>
    <td>Unvalidated Recipient</td>
    <td>No recipient checksum / domain verification</td>
  </tr>

  <!-- ================================= -->
  <!-- 12. Communication Security -->
  <!-- ================================= -->


  <tr>
  <td rowspan="4">Communication Security</td>
  <td rowspan="4">Communication Weakness</td>

  <td>Cross-Domain Channels</td>
  <td>Unsafe cross-domain communication or untrusted messaging endpoints</td>
</tr>

<tr>
  <td>Communication Encryption</td>
  <td>Unencrypted or weakly encrypted communication channels</td>
</tr>

<tr>
  <td>Content Security Policy</td>
  <td>Missing or weak CSP allowing unauthorized scripts or unsafe resource loading</td>
</tr>

<tr>
  <td>Origin Validation</td>
  <td>Insufficient origin checks for external messages or embedded frames</td>
</tr>





</table>
