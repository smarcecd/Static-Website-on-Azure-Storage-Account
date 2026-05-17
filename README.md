# Static-Website-on-Azure-Storage-Account

# Deploy a Static Website on Azure Storage Account

Hosting a static website on Azure Storage is one of the simplest, most scalable, and cost‑effective ways to publish web content. Whether you're building a portfolio, documentation site, or a lightweight business page, Azure Static Website Hosting gives you global reach, built‑in HTTPS, and zero server maintenance.


---


## 📌 Overview


This lab walks you through deploying a static website using Azure Blob Storage — from creating the storage account to enabling static hosting, uploading your files, and accessing your live site.


## 📘 What Is a Static Website?


A static website is made up of pre‑built HTML, CSS, JavaScript, and media files served directly to the browser — no backend or server‑side processing required.

Static sites are ideal for:
 - Personal portfolios
 - Documentation sites
 - Marketing landing pages
 - Blogs built with static generators (Hugo, Jekyll, etc.)


## 🌐 Why Host on Azure Storage?


Azure Storage Static Website Hosting provides:

| Feature | Benefit | 
|--------|--------|
| Low Cost | Pay only for the storage you use |
| Global Reach | Content served from Microsoft’s global CDN |
| HTTPS Support | Built‑in SSL certificates |
| Custom Domains | Easily map your own domain |
| Zero Maintenance | No servers, patches, or backend to manage |


---


##  🚀 Step‑by‑Step Deployment Guide


## 🔹 Step 1: Create a Storage Account


Sign in to the **Azure Portal**

Select **Create a resource** → **Storage** → **Storage account**

Configure the required fields:

| Setting | Value |
|--------|--------|
| Resource Group | Select one or create a new one static-rg |
| Storage account name | staticweb |
| Region | East US|
| Performance tier | Standard |
| Redundancy | LRS |

Click **Review + Create**

Select **Create**
 

---
 

## 🔹 Step 2: Enable Static Website Hosting

Open your newly created **Storage Account**

In the left menu, under **Data Management** select **Static website**

Switch Static website to **Enabled**

Configure the following:

Index document name: index.html (this should be the name of your html file)

Error document path: 404.html

Click Save

**Note:** 
 - Copy the Primary endpoint URL — this is your live website URL
 - The **$web** container will be created automatically when static hosting is enabled.


---


## 🔹 Step 3: Upload Your Website Files


To  upload your static files using **Azure Portal**:

On the **storage account** under **Data storage** select **Containers**

Select the **$web** container

Click on **Upload** and search for the static website file saved on your computer

Click Upload


---


## 🔹 Step 4: Access Your Live Website

Once your files are uploaded, open the Primary endpoint URL in a browser.
Your static website is now live and globally accessible.
