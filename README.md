# OWASP Juice Shop — Web Application Security Assessment

## Project Overview
This project documents a hands-on security assessment of OWASP Juice Shop, an intentionally vulnerable web application, deployed locally using Docker.

The objective was to understand HTTP communication, analyze web application behavior, and identify potential security weaknesses through manual testing.

## Lab Environment
- **Operating System:** Kali Linux
- **Target:** OWASP Juice Shop (localhost:3000)
- **Tools:** Burp Suite Community Edition, Docker, cURL, Chrome Developer Tools
- **Testing Scope:** Locally hosted educational application

## Assessment Areas

| Area | Observation |
|---|---|
| Authentication | Successful and unsuccessful login responses examined |
| Password Recovery | Password reset workflow tested in the local lab |
| Security Headers | CORS and browser security headers reviewed |
| Configuration | Application configuration endpoint inspected |
| Error Handling | Internal stack trace observed in an error response |
| Session Management | Authentication token and cookie behavior examined |

## Key Findings
1. **Verbose Error Handling:** A nonexistent API route produced an HTTP 500 response containing an internal stack trace.
2. **Permissive CORS Header:** `Access-Control-Allow-Origin: *` was observed. Security impact requires additional validation.
3. **Application Configuration Exposure:** The configuration endpoint returned application settings. Sensitivity of the exposed data requires further review.
4. **Authentication and Session Behavior:** Login, token-based authentication, and unauthenticated requests were examined.

These observations are not all confirmed exploitable vulnerabilities.

## Methodology
1. Set up OWASP Juice Shop locally.
2. Configure Burp Suite as an HTTP interception proxy.
3. Capture and inspect application requests.
4. Replay selected requests using Burp Repeater.
5. Compare successful and unsuccessful responses.
6. Record observations and supporting evidence.
7. Document potential impact and remediation recommendations.

## Learning Outcomes
- Understanding HTTP requests and responses
- Using Burp Suite Proxy and Repeater
- Inspecting authentication workflows
- Reviewing application security headers
- Recognizing information disclosure through error messages
- Preparing structured vulnerability assessment reports

## Disclaimer
All testing was performed in a locally hosted, intentionally vulnerable educational environment. This project is intended solely for authorized cybersecurity learning and portfolio documentation.
