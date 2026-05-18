# Architectural Diagram – Static Website on Azure Storage Account

This document explains the architecture behind hosting a static website using Azure Storage Account Static Website Hosting.

---

## 🏗️ High-Level Architecture Diagram

```mermaid
flowchart TD

A[User Browser] -->|HTTPS Request| B[Azure Static Website Endpoint]

B --> C[$web Container<br>Static Files (HTML, CSS, JS, Images)]

C -->|Serves Content| A
```
---

## 🔍 Component Breakdown
**1. User Browser**
The end user accessing the website from any device.
Requests static content via HTTPS.

**2. Azure Static Website Endpoint**
Generated automatically when static hosting is enabled.
Example format:

**https://<storage-account-name>.z13.web.core.windows.net/**

This endpoint:
 - Serves the index document (index.html)
 - Handles 404 errors using the configured error document
 - Requires no server or backend configuration

**3. Azure Storage Account**
The core service hosting the website.
Key features:
 - Highly available object storage
 - Built-in HTTPS
 - Global redundancy options
 - Pay-as-you-go pricing

**4. $web Container**
A special blob container created automatically when static hosting is enabled.
It stores:
 - index.html
 - 404.html
 - CSS files
 - JavaScript files
 - Images
 - Any other static assets

Azure serves files directly from this container.

---

## 🌐 Request Flow Summary

User enters the website URL.

DNS resolves the Azure Static Website endpoint.

Azure retrieves the requested file from the $web container.

The file is delivered to the browser over HTTPS.

Browser renders the static content.

---

## 📦 Optional Enhancements

- **Azure CDN:** Improves global performance by caching static assets closer to users.
- **Custom Domain:** Wit it, you can map: www.yourdomain.com, to the Azure static endpoint.
- **CI/CD Pipeline:** Automate deployments using:
                    - GitHub Actions
                    - Azure DevOps Pipelines

  ---

## 🎯 Final Notes

This architecture is:
- Serverless
- Scalable
- Cost‑efficient
- Ideal for lightweight websites
- It demonstrates how Azure Storage can be used as a simple yet powerful hosting platform for static content
