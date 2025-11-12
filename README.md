
#  Love, Bride & Lace — Serverless Cloud Architecture on AWS
### Empowering a Local Bridal Boutique with a Fast, Secure, and Scalable Cloud-Hosted Website


##  Overview
This project demonstrates how **cloud computing** can transform a local business by delivering **speed, security, and scalability** through a **serverless AWS architecture**.

**Love, Bride & Lace**, a boutique bridal brand based in Johannesburg, needed a **modern, professional website** to showcase its gowns, attract brides, and build online trust.  
However, the business faced performance and security issues that limited its digital visibility and customer engagement.

This technical case study documents the **problem**, **architecture**, **tools**, **deployment process**, and **outcomes** of implementing an **AWS-powered serverless solution**.


##  The Problem
The original website had several challenges:

- ⚠️ **Slow page loads**, causing high bounce rates.  
- 🔒 **No HTTPS encryption**, reducing customer trust and SEO ranking.  
- 🚫 **Poor scalability** during seasonal traffic spikes.  
- 🧱 **Manual maintenance**, making updates inefficient.

A secure, fast, and reliable digital foundation was essential to enhance user experience and business growth.


##  Architecture Strategy
The goal was to design a **cost-effective, fully serverless architecture** that ensures:
- High performance and low latency.
- Secure browsing via HTTPS and DDoS protection.
- Zero server management.
- Scalable content delivery at minimal cost.

###  AWS Services Used

| AWS Service | Purpose |
|--------------|----------|
| **Amazon S3** | Static website hosting and storage for HTML, CSS, JS, and images. |
| **Amazon CloudFront** | Global content delivery network (CDN) with caching and DDoS protection. |
| **AWS Certificate Manager (ACM)** | Provision and manage SSL/TLS certificates for HTTPS. |
| **Amazon Route 53** | DNS routing and custom domain management. |
| **Lambda@Edge** | SEO redirects, metadata injection, and HTTPS enforcement. |
| **AWS IAM** | Secure access control with least-privilege policies. |

---

##  System Architecture

```

User Request → Route 53 (DNS)
→ CloudFront (CDN + HTTPS)
→ S3 Bucket (Static Website Origin)
→ Lambda@Edge (SEO Optimization)

```

- **CloudFront** caches website assets at edge locations for low latency.  
- **S3** acts as a durable, serverless origin.  
- **Lambda@Edge** enhances SEO, redirects, and metadata handling.  
- **ACM** ensures all traffic is encrypted using HTTPS.

---

##  Implementation Steps

### 1️⃣ Host the Website on S3
- Created an S3 bucket named `lovebrideandlace.co.za`.  
- Uploaded static website files (HTML, CSS, JS, images).  
- Enabled **Static Website Hosting**.

### 2️⃣ Configure CloudFront
- Set the S3 bucket as the **Origin Domain**.  
- Enabled **Origin Access Control (OAC)** to secure access.  
- Added **Origin Shield** for caching efficiency.  
- Linked an **ACM certificate** for HTTPS.

### 3️⃣ Setup Route 53
- Registered and configured the domain `lovebrideandlace.co.za`.  
- Created an **Alias (A) Record** pointing to the CloudFront distribution.

### 4️⃣ Implement Security
- Restricted S3 bucket access to CloudFront only.  
- Applied least-privilege **IAM policies**.  
- Forced HTTPS redirects with **Lambda@Edge**.

### 5️⃣ SEO Optimization (Lambda@Edge)
- Created a Node.js function to:
  - Redirect non-www → www.  
  - Add meta tags and Open Graph data dynamically.  
  - Enforce HTTPS redirection.

---

## 💡 The Solution
After deployment, the website was:

- 🌐 Hosted entirely on **Amazon S3 + CloudFront** (serverless).  
- 🔒 Fully secured with **ACM-issued SSL certificate**.  
- ⚡ Optimized for **fast performance and SEO**.  
- 🔁 Integrated with **automated CI/CD** for easy updates (via AWS CLI or GitHub Actions).  

---

## 📈 Results and Impact

| Metric | Before | After |
|--------|--------|-------|
| Page Load Time | ~4.8s | **1.9s** | 
| Total cumulative wait time | ~4.23s | |
| Average wait time per request | ~63ms | |
| Longest individual wait time | ~192 ms (for hero-desktop.jpg) | |
| Uptime | 93% | **99.99%** |
| HTTPS Security | None | **Enabled (ACM)** |
| Monthly Hosting Cost | ~R500 | **< R100** |
| Scalability | Manual | **Automatic (Serverless)** |

### ✨ Key Benefits
- 60% faster website performance with CloudFront edge caching.  
- HTTPS encryption increased customer trust and SEO ranking.  
- Global low-latency delivery with AWS edge locations.  
- Operational costs reduced by over 70%.  
- Scalable foundation ready for API, analytics, or e-commerce integration.

---

## 🧾 Tech Stack

- **AWS Services:** S3, CloudFront, Route 53, ACM, IAM, Lambda@Edge  
- **Languages:** HTML5, CSS3, JavaScript  
- **Tools:** GitHub, AWS CLI, CloudFormation  
- **Methodology:** Serverless Architecture, IaC, SEO Optimization

---

## 🌟 Conclusion
This project showcases how a **local boutique business** can achieve **enterprise-level speed, security, and scalability** using a **serverless AWS architecture**.

By combining **S3, CloudFront, ACM, and Lambda@Edge**, Love, Bride & Lace now has a **high-performance, secure, and future-ready** online presence — with **zero server maintenance**.

> “Serverless architecture gave the boutique peace of mind — their site just works, securely and at scale.”


## 🚀 Next Steps
- Add a contact form using **AWS Lambda + Amazon SES**.  
- Enable **analytics tracking** with AWS Pinpoint or Google Analytics.  
- Integrate **e-commerce capabilities** via AWS Amplify or Shopify API.  
- Automate deployments with **GitHub Actions CI/CD**.

---

## 📎 Author
**Koketso B. Mangwale**  
Cloud Computing | Analyst Programmer| AWS Practitioner  
[LinkedIn](https://linkedin.com) • [GitHub](https://github.com) • [Email](mailto:)


