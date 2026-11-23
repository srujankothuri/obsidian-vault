---
tags: [companies, co-op, job-search, industry]
---

# Tech Companies – What They Do

## Quick Reference

| Company | Category | One-liner | HQ |
|---|---|---|---|
| [[#IBM]] | Big Tech | Hybrid cloud, AI (watsonx), consulting, mainframes | Armonk, NY |
| [[#Snowflake]] | Data | Cloud data warehouse / data platform | Bozeman, MT |
| [[#Databricks]] | Data & AI | Lakehouse platform for data + ML/AI | San Francisco |
| [[#MongoDB]] | Databases | NoSQL document database + Atlas cloud | New York City |
| [[#Elastic]] | Search | Elasticsearch: search, logs, security | San Francisco / Amsterdam |
| [[#Cloudflare]] | Network & Security | CDN, DDoS protection, DNS, edge compute | San Francisco |
| [[#Akamai]] | Network & Security | Original CDN, now security + cloud | Cambridge, MA |
| [[#Netlify]] | Web Hosting | Git-based frontend hosting & deploys | San Francisco |
| [[#GitLab]] | DevOps | All-in-one DevSecOps + CI/CD | Fully remote |
| [[#Atlassian]] | Collaboration | Jira, Confluence, Trello, Bitbucket | San Francisco (founded Sydney) |
| [[#HashiCorp]] | Infra as Code | Terraform, Vault (now IBM) | San Francisco |
| [[#Red Hat]] | Open Source | RHEL, OpenShift, Ansible (now IBM) | Raleigh, NC |
| [[#Datadog]] | Observability | Monitoring: metrics, logs, traces | New York City |
| [[#CrowdStrike]] | Security | Endpoint protection (Falcon) | Austin, TX |
| [[#Palo Alto Networks]] | Security | Firewalls + broad security platform | Santa Clara, CA |
| [[#Zscaler]] | Security | Zero trust cloud security, VPN replacement | San Jose, CA |
| [[#Okta]] | Identity | SSO, MFA, Auth0 | San Francisco |
| [[#SAP]] | Enterprise Apps | ERP for large companies | Walldorf, Germany |
| [[#Salesforce]] | Enterprise Apps | #1 CRM, Slack, Tableau, Agentforce | San Francisco |
| [[#ServiceNow]] | Enterprise Apps | IT service management + workflows | Santa Clara, CA |
| [[#Pegasystems]] | Enterprise Apps | Low-code workflow + AI decisioning | Boston area |
| [[#PTC]] | Engineering Software | CAD (Creo, Onshape) + PLM (Windchill) | Boston (Seaport) |
| [[#HubSpot]] | SMB SaaS | CRM for small/mid businesses | Cambridge, MA |
| [[#Klaviyo]] | Marketing Tech | Email/SMS marketing for e-commerce | Boston |
| [[#Intuit]] | Fintech | TurboTax, QuickBooks, Credit Karma, Mailchimp | Mountain View, CA |
| [[#Stripe]] | Fintech | Online payments APIs & financial infrastructure | San Francisco / Dublin |
| [[#Twilio]] | Communications | SMS, voice, email APIs | San Francisco |

---

# Big Tech

## IBM

IBM is one of the oldest and largest technology companies. Today it focuses on **hybrid cloud, AI, and consulting for large enterprises**, plus the mainframe hardware that much of the world's banking and airline infrastructure still runs on.

**Main things it does:**
- **Hybrid cloud software:** built around [[#Red Hat]] (OpenShift, RHEL, Ansible), letting companies run apps across their own data centers and public clouds. It also owns [[#HashiCorp]] (Terraform, Vault) plus tools like Instana (observability), Turbonomic, and Apptio.
- **AI:** **watsonx**, a platform for building, training, and governing AI models for businesses, along with its own Granite family of open models.
- **IBM Consulting:** one of the largest IT consulting businesses, helping companies with cloud migration, AI adoption, and business transformation.
- **Infrastructure:** **IBM Z mainframes** (used by most major banks for transaction processing), Power servers, and storage.
- **Quantum computing:** one of the leaders in building quantum computers and the Qiskit open-source quantum SDK.

**Business model:** Software subscriptions (its biggest profit driver), consulting fees, and hardware sales and financing, sold almost entirely to large enterprises and governments.

**Background:** Founded in 1911 (renamed IBM in 1924), headquartered in Armonk, New York. Historically famous for the IBM PC, the Deep Blue chess computer, and Watson winning Jeopardy! It sold its PC business to Lenovo in 2005 and spun off its IT infrastructure services business as Kyndryl in 2021. Competitors: Microsoft, AWS, and Google (cloud and AI), Accenture and Deloitte (consulting), Oracle, HPE, and Dell.

---

# Data, Databases & Search

## Snowflake

Snowflake is a cloud data company. Its core product is a **cloud data platform** (originally a data warehouse) that lets organizations store, process, and analyze large amounts of data without managing their own hardware or database infrastructure.

**Key features:**
- **Runs on top of the major clouds** (AWS, Azure, Google Cloud) rather than its own data centers, and works across all three.
- **Separates storage from compute**, so companies can scale processing power up or down independently of how much data they store and pay only for what they use. This was its big architectural innovation.
- **Data sharing** lets organizations share live data securely with partners or customers without copying it, plus a marketplace for buying and selling datasets.
- **Beyond SQL analytics**, it has expanded into data engineering, data lakes (including Apache Iceberg support), running Python and other code through Snowpark, and AI/ML features like Cortex for using large language models on company data.

**Business model:** Consumption-based pricing. Customers pay for the compute and storage they use rather than a flat license.

**Background:** Founded in 2012, headquartered in Bozeman, Montana (with major offices in San Mateo and elsewhere), and went public in 2020 in what was then the largest software IPO ever. Main competitors: Databricks, Google BigQuery, Amazon Redshift, and Microsoft Fabric.

**In short:** Companies use Snowflake as the central place to collect their data from many sources and run analytics, reporting, and increasingly AI workloads on it.

## Databricks

Databricks is a **data and AI platform** that lets companies store, process, and analyze huge amounts of data and build machine learning and AI models on it, all in one place.

**Main things it does:**
- **Lakehouse platform:** combines a data lake (cheap storage for raw data) with a data warehouse (fast SQL analytics), built on its open-source **Delta Lake** format.
- **Apache Spark at scale:** runs large data processing and engineering pipelines. Its founders created Spark.
- **ML and AI:** MLflow for tracking and deploying models, plus **Mosaic AI** for training, fine-tuning, and serving LLMs and building AI agents.
- **Governance and SQL:** Unity Catalog for managing data access, and Databricks SQL for BI and analytics.

**Business model:** Consumption-based. Customers pay for compute used (measured in "Databricks Units"), running on AWS, Azure, or Google Cloud.

**Background:** Founded in 2013 by the creators of Apache Spark at UC Berkeley, headquartered in San Francisco, and still **private** (one of the most valuable private tech companies). Acquired MosaicML in 2023 and Tabular (the Apache Iceberg creators) in 2024. Biggest rival is **Snowflake**, along with Google BigQuery and Microsoft Fabric.

## MongoDB

MongoDB is a **database company** best known for its **NoSQL document database**, which stores data as flexible JSON-like documents instead of rigid rows and tables.

**Main things it does:**
- **MongoDB database:** a document database popular with developers because the schema can evolve easily as an app changes.
- **MongoDB Atlas:** the fully managed cloud version running on AWS, Azure, and Google Cloud. It's now the bulk of the business.
- **Built-in extras:** full-text search, vector search for AI apps, time-series data, and stream processing inside the same platform.

**Business model:** Atlas is consumption-based. Self-managed Enterprise Advanced is sold as subscriptions. A free Community edition drives developer adoption.

**Background:** Founded in 2007, headquartered in New York City, public since 2017. Competitors: Amazon DynamoDB and DocumentDB, Azure Cosmos DB, Couchbase, and PostgreSQL (which increasingly handles JSON well).

## Elastic

Elastic is the company behind **Elasticsearch**, a fast **search and analytics engine** used to search huge amounts of text, logs, and data in near real time.

**Main things it does:**
- **Search:** powers search bars in apps and websites, plus enterprise search and vector/semantic search for AI.
- **Observability:** the ELK stack (Elasticsearch, Logstash, Kibana) is a classic setup for collecting and visualizing logs and metrics.
- **Security:** SIEM and endpoint security built on the same engine.

**Business model:** Open-core. The core is free, with paid subscriptions and the managed Elastic Cloud service.

**Background:** Founded in 2012, headquartered in San Francisco and Amsterdam, public since 2018. In 2021 it changed its license, which led AWS to fork the project as **OpenSearch**; it later added an open-source license option back in 2024. Competitors: OpenSearch, Datadog, Splunk, and Algolia (for search).

---

# Networking, CDN & Web Hosting

## Cloudflare

Cloudflare is a networking and security company. Its global network sits between websites/apps and their users, making them **faster, more secure, and more reliable**. A large share of the internet's traffic passes through it.

**Main things it does:**
- **CDN (content delivery network):** caches website content on servers in hundreds of cities worldwide so pages load faster for users wherever they are.
- **DDoS protection and security:** absorbs and blocks attacks that try to overwhelm sites with traffic, plus a web application firewall (WAF), bot management, and SSL/TLS encryption.
- **DNS:** runs one of the fastest DNS services, including the free public resolver 1.1.1.1.
- **Zero Trust / enterprise security:** tools that replace corporate VPNs and secure employee access to internal apps (often called SASE).
- **Developer platform:** Cloudflare Workers lets developers run code at the "edge" (close to users) without managing servers, alongside storage products like R2 (object storage), D1 (database), KV, and AI inference through Workers AI.

**Business model:** Freemium. Many small sites use it for free, while businesses and enterprises pay subscriptions for advanced features.

**Background:** Founded in 2009, headquartered in San Francisco, public since 2019. Competitors by product: Akamai and Fastly (CDN and security), Zscaler (zero trust), AWS/Vercel (edge computing).

**In short:** Cloudflare is the layer that speeds up and protects websites and apps, and increasingly a platform for building and running them.

## Akamai

Akamai is one of the **original content delivery networks** and now a combined **cybersecurity, content delivery, and cloud computing** company.

**Main things it does:**
- **Content delivery:** one of the world's largest distributed networks, delivering websites, video streaming, and software downloads for major companies.
- **Security:** web application firewall, DDoS protection, API security, and Guardicore microsegmentation (which limits how attackers can move inside a network). Security is now its biggest business.
- **Cloud computing:** after acquiring **Linode** in 2022, it offers cloud servers and is building out distributed edge computing.

**Business model:** Contracts and subscriptions, mainly with large enterprises, media companies, and governments.

**Background:** Founded in 1998 out of **MIT**, headquartered in **Cambridge, Massachusetts**, public since 1999. A significant Boston-area tech employer. Competitors: Cloudflare, Fastly, AWS CloudFront, and the major cloud providers.

## Netlify

Netlify is a **platform for deploying and hosting websites and frontend web apps**, especially those built with modern JavaScript frameworks.

**Main things it does:**
- **Git-based deployment:** connect a GitHub repo and every push automatically builds and deploys the site.
- **Global CDN hosting:** serves sites fast from edge locations worldwide.
- **Serverless and edge functions:** run backend code without managing servers.
- **Developer conveniences:** deploy previews for every pull request, forms, authentication, and rollbacks.

**Business model:** Freemium. A generous free tier for individuals, with paid plans for teams and enterprises.

**Background:** Founded in 2014, headquartered in San Francisco, **private**. Its founders coined the term **"Jamstack"**. Main competitor is **Vercel**, along with Cloudflare Pages, AWS Amplify, and Render.

---

# DevOps, Developer Tools & Open Source

## GitLab

GitLab is a **DevSecOps platform**: a single application covering the whole software development lifecycle, from planning and writing code to testing, securing, and deploying it.

**Main things it does:**
- **Source code management:** Git repositories, merge requests, and code review.
- **CI/CD:** built-in pipelines that automatically build, test, and deploy code. One of its biggest strengths.
- **Security scanning:** finds vulnerabilities in code and dependencies as part of the pipeline.
- **Planning and AI:** issue tracking, boards, and GitLab Duo AI for coding assistance.

**Business model:** Open-core. A free tier, plus paid Premium and Ultimate subscriptions priced per user, available as SaaS (GitLab.com) or self-managed.

**Background:** Started as an open-source project in 2011, became a company in 2014, public since 2021. Famous for being **fully remote** with no physical headquarters. Main competitor is **GitHub** (Microsoft), along with Atlassian Bitbucket and Jenkins for CI/CD.

## Atlassian

Atlassian makes **collaboration and project management software** for software teams and, increasingly, all business teams.

**Main things it does:**
- **Jira:** the most widely used tool for tracking tasks, bugs, and sprints in agile software teams.
- **Confluence:** a team wiki for documentation and knowledge sharing.
- **Jira Service Management:** IT help desk and ticketing.
- **Other products:** Bitbucket (Git hosting), Trello (simple boards), Loom (video messaging), and Rovo (AI search and agents across a company's tools).

**Business model:** Subscriptions priced per user, now mostly cloud-based after it ended support for self-hosted Server products in 2024. Famous for growing mostly through word of mouth rather than a large sales team.

**Background:** Founded in 2002 in Sydney, Australia, now headquartered in San Francisco, public since 2015. Competitors: Monday.com, Asana, Linear, Notion, GitHub and GitLab (dev workflows), and ServiceNow (IT service management).

## HashiCorp

HashiCorp makes **infrastructure automation tools** that help teams provision, secure, and run cloud infrastructure using code.

**Main things it does:**
- **Terraform:** the most widely used "infrastructure as code" tool. You describe servers, networks, and databases in config files, and Terraform creates them across any cloud.
- **Vault:** securely stores and manages secrets such as API keys, passwords, and certificates.
- **Consul and Nomad:** service networking/discovery and workload scheduling.

**Business model:** Free tools plus paid enterprise editions and the managed HCP (HashiCorp Cloud Platform).

**Background:** Founded in 2012, based in San Francisco. In 2023 it switched to a more restrictive license, which led the community to fork Terraform into **OpenTofu**. **IBM acquired HashiCorp in 2025** for about $6.4 billion, pairing it with Red Hat. Competitors: Pulumi, OpenTofu, AWS CloudFormation, and CyberArk (for secrets).

## Red Hat

Red Hat is an **enterprise open-source software company**, best known for **Red Hat Enterprise Linux (RHEL)**, the Linux operating system many large companies run their servers on.

**Main things it does:**
- **RHEL:** a stable, certified, supported Linux distribution for enterprises.
- **OpenShift:** an enterprise Kubernetes platform for building, deploying, and managing containerized apps across hybrid clouds.
- **Ansible:** an IT automation tool for configuring and managing servers at scale.
- **AI and middleware:** RHEL AI and OpenShift AI for running models, plus application middleware.

**Business model:** The software is open source and free to use, but companies pay **subscriptions for support, security updates, certification, and reliability guarantees**. The first company to make that model work at billion-dollar scale.

**Background:** Founded in 1993, headquartered in Raleigh, North Carolina. **IBM acquired it in 2019 for about $34 billion**, and it operates as a fairly independent unit within IBM. Competitors: SUSE, Canonical (Ubuntu), VMware/Broadcom, and the cloud providers' own platforms.

---

# Observability

## Datadog

Datadog is a **monitoring and observability platform** for cloud applications and infrastructure. It collects metrics, logs, and traces from servers, containers, databases, and code, then gives engineering teams dashboards and alerts to see how their systems are performing and to debug problems.

**Main things it does:**
- **Infrastructure monitoring:** tracks the health of servers, cloud services, and Kubernetes clusters.
- **APM (application performance monitoring):** traces requests across microservices to find slow or failing code.
- **Log management:** collects and searches logs from everything in one place.
- **Security and more:** cloud security monitoring, real user monitoring (frontend performance), synthetic tests, incident management, and LLM observability for AI apps.

**Business model:** Usage-based SaaS subscriptions, typically priced per host, per GB of logs, and so on. Customers often start with one product and expand into others.

**Background:** Founded in 2010, headquartered in New York City, public since 2019. Competitors: Splunk (now Cisco), New Relic, Dynatrace, Elastic, and open-source stacks like Grafana + Prometheus + OpenTelemetry.

---

# Cybersecurity & Identity

## CrowdStrike

CrowdStrike is a **cybersecurity company** focused on **endpoint protection**, meaning it secures laptops, servers, and other devices against hackers and malware.

**Main things it does:**
- **Falcon platform:** a lightweight agent installed on devices that detects and blocks threats in real time, using cloud-based AI rather than traditional signature-based antivirus.
- **EDR/XDR:** detection and response tools that let security teams investigate and contain attacks.
- **Threat intelligence and services:** tracks hacking groups and offers incident response when companies get breached.
- **Expanding coverage:** cloud security, identity protection, a next-gen SIEM, and AI-driven security tools.

**Business model:** Subscription SaaS, with customers adding more Falcon "modules" over time.

**Background:** Founded in 2011, headquartered in Austin, Texas, public since 2019. Widely known for the **July 2024** faulty update that crashed millions of Windows machines worldwide, one of the biggest IT outages ever. Competitors: Microsoft Defender, Palo Alto Networks, SentinelOne, and Zscaler.

## Palo Alto Networks

Palo Alto Networks is one of the **largest cybersecurity companies**, offering a broad "platform" of security products.

**Main things it does:**
- **Network security:** next-generation firewalls, the product it was founded on, in both hardware and software form.
- **Prisma:** SASE (secure access for remote workers) and cloud security for workloads on AWS, Azure, and GCP.
- **Cortex:** security operations, including XDR, a SIEM replacement (XSIAM), and automated incident response.
- **Unit 42:** threat research and incident response services.

**Business model:** A mix of hardware, software subscriptions, and services, with a big push to get customers to consolidate onto its whole platform.

**Background:** Founded in 2005, headquartered in Santa Clara, California, public since 2012. Grows heavily through acquisitions, including a deal announced in 2025 to buy identity security company CyberArk. Competitors: Fortinet, Cisco, CrowdStrike, Zscaler, and Check Point.

## Zscaler

Zscaler is a **cloud security company** focused on **zero trust**: never automatically trusting any user or device, even inside a company network.

**Main things it does:**
- **Zscaler Internet Access (ZIA):** routes employees' internet traffic through Zscaler's cloud to block malware, phishing, and data leaks, wherever they're working.
- **Zscaler Private Access (ZPA):** gives employees secure access to internal apps, replacing traditional VPNs.
- **Zero Trust Exchange:** the overall cloud platform connecting users, devices, and apps securely, plus data protection and AI-powered threat detection.

**Business model:** Subscription SaaS, usually priced per user, sold mainly to large enterprises.

**Background:** Founded in 2007, headquartered in San Jose, California, public since 2018. A leader in the **SASE/SSE** market. Competitors: Palo Alto Networks (Prisma), Netskope, Cloudflare One, and Cisco.

## Okta

Okta is an **identity and access management** company. It controls **who can log in to what**, for both employees and customers.

**Main things it does:**
- **Workforce identity:** single sign-on (log in once, access all work apps), multi-factor authentication, and user provisioning.
- **Customer identity (Auth0):** developers use Auth0 to add login, signup, and social login to their own apps.
- **Identity security:** governance, privileged access, and detecting identity-based attacks.

**Business model:** Subscription SaaS, usually priced per user.

**Background:** Founded in 2009, headquartered in San Francisco, public since 2017. Acquired Auth0 in 2021 for about $6.5 billion. Main competitor is Microsoft Entra ID (formerly Azure AD), along with Ping Identity and CyberArk.

---

# Enterprise Applications

## SAP

SAP is the world's leading maker of **ERP (enterprise resource planning) software**, the systems large companies use to run core operations such as finance, supply chain, manufacturing, procurement, and HR.

**Main things it does:**
- **S/4HANA:** its flagship ERP suite, built on its own **HANA** in-memory database.
- **Cloud business apps:** SuccessFactors (HR), Ariba (procurement), Concur (travel and expenses), and others.
- **Business Technology Platform and AI:** tools to extend and integrate SAP systems, plus its Joule AI assistant.

**Business model:** Historically licenses plus maintenance fees, now shifting heavily to **cloud subscriptions** ("RISE with SAP" pushes customers to migrate to the cloud).

**Background:** Founded in 1972 in Germany, headquartered in Walldorf, and **Europe's largest software company**. Most of the world's largest companies run on SAP. Competitors: Oracle, Microsoft Dynamics, Workday, and Infor.

## Salesforce

Salesforce is the world's largest **CRM (customer relationship management)** software company. It helps businesses manage their sales, customer service, and marketing.

**Main things it does:**
- **Core clouds:** Sales Cloud (tracking leads and deals), Service Cloud (customer support), Marketing Cloud, and Commerce Cloud.
- **Acquired platforms:** **Slack** (team chat), **Tableau** (data visualization), and **MuleSoft** (connecting systems through APIs).
- **Data and AI:** Data Cloud for unifying customer data, and **Agentforce**, its big push into AI agents that handle sales and support tasks.

**Business model:** Subscription SaaS priced per user. One of the **pioneers of the SaaS model**.

**Background:** Founded in 1999 by Marc Benioff, headquartered in San Francisco. Known for massive acquisitions, including Slack for about $27.7 billion in 2021 and an agreement in 2025 to acquire data management company Informatica. Competitors: Microsoft Dynamics, HubSpot, Oracle, SAP, and Zendesk.

## ServiceNow

ServiceNow is a **workflow automation platform** for large enterprises, best known for **IT service management**: the systems that handle IT help desk tickets, incidents, and requests.

**Main things it does:**
- **IT service management (ITSM):** ticketing, incident handling, and change management for IT teams. Its core product.
- **Other workflows:** HR service delivery, customer service, IT operations, and security operations on the same platform.
- **Now Platform:** a low-code platform where companies build their own internal apps and workflows.
- **AI:** Now Assist and AI agents that automate tickets and requests.

**Business model:** Subscription SaaS, usually priced per user, sold to large enterprises and governments.

**Background:** Founded in 2004, headquartered in Santa Clara, California, public since 2012. One of the fastest-growing large enterprise software companies. Competitors: Atlassian (Jira Service Management), BMC, Salesforce, and Freshworks.

## Pegasystems

Pegasystems (Pega) makes a **low-code platform for automating business processes and customer interactions** at large enterprises. Companies use it to build apps that handle complex workflows like loan applications, insurance claims, and customer service cases.

**Main things it does:**
- **Pega Platform (Pega Infinity):** a low-code environment for building workflow and case management apps, where a "case" is something like a claim or dispute that moves through many steps and people.
- **Customer Decision Hub:** an AI decisioning engine that picks the "next best action" for each customer in real time, such as which offer to show or when to intervene before a customer leaves.
- **Customer service and sales apps:** prebuilt applications for call centers and service teams.
- **GenAI tools:** Pega GenAI Blueprint, which uses AI to design workflow apps from a description.

**Business model:** Subscriptions, both cloud (Pega Cloud) and licenses for self-managed deployments. Customers are mostly **large banks, insurers, healthcare companies, telecoms, and governments**.

**Background:** Founded in 1983 by Alan Trefler (who still runs it), headquartered in the Boston area, public since 1996. Has its own certification track (CSA, CSSA) that many enterprise developers get, useful to know for Pega developer roles. Competitors: Appian, ServiceNow, Salesforce, IBM, and UiPath.

## PTC

PTC makes **software for designing, manufacturing, and servicing physical products**, used by engineers at companies that build cars, aircraft, machinery, and medical devices.

**Main things it does:**
- **Creo:** CAD software for 3D modeling and engineering design.
- **Onshape:** a fully cloud-based CAD tool (acquired in 2019), popular with startups and students because it runs in the browser.
- **Windchill:** PLM (product lifecycle management) software that manages a product's data, parts, and changes from design through retirement.
- **Codebeamer and ServiceMax:** application lifecycle management for software in products, and field service management for maintaining equipment.

**Business model:** Subscriptions, sold mainly to manufacturing companies.

**Background:** Founded in 1985 as Parametric Technology Corporation, headquartered in **Boston's Seaport district**, public since 1989. Competitors: **Dassault Systèmes** (SolidWorks, CATIA), **Siemens** (NX, Teamcenter), and **Autodesk**.

---

# SMB, Marketing, Fintech & Communications

## HubSpot

HubSpot is a **CRM platform for small and mid-sized businesses**, covering marketing, sales, and customer service in one integrated system.

**Main things it does:**
- **Free CRM:** a free core for managing contacts, companies, and deals, which brings in new users.
- **Hubs:** Marketing Hub (email, ads, SEO, landing pages), Sales Hub, Service Hub, Content Hub (website CMS), Operations Hub (data syncing), and Commerce Hub.
- **AI:** Breeze, its AI assistant and agents built into the platform.

**Business model:** Freemium, with tiered subscriptions (Starter, Professional, Enterprise) that customers upgrade through as they grow.

**Background:** Founded in 2006 by two MIT grads, headquartered in **Cambridge, Massachusetts**, public since 2014. Popularized the term **"inbound marketing"** and is one of Boston's biggest tech employers. Main competitor is **Salesforce**, along with Zoho and Pipedrive.

## Klaviyo

Klaviyo is a **marketing automation platform for e-commerce brands**. It helps online stores send personalized emails, texts, and push notifications based on how customers shop.

**Main things it does:**
- **Email and SMS marketing:** automated flows like abandoned-cart reminders, welcome series, and post-purchase messages, plus campaigns.
- **Customer data platform:** collects shopping behavior (browsing, purchases, clicks) into unified customer profiles for detailed segmentation.
- **Predictive analytics and AI:** predicts things like a customer's next purchase date and lifetime value, and uses AI to write and optimize messages.
- **Deep e-commerce integrations:** especially **Shopify**, which is both a key partner and an investor.

**Business model:** Subscriptions priced by the number of contacts and messages sent, so revenue grows as customers' businesses grow.

**Background:** Founded in 2012 in Boston, headquartered in **downtown Boston**, public since its 2023 IPO. One of the city's fastest-growing tech companies. Competitors: Mailchimp (Intuit), Braze, Attentive, Salesforce Marketing Cloud, and HubSpot.

## Intuit

Intuit makes **financial software for consumers, small businesses, and accountants**.

**Main things it does:**
- **TurboTax:** the most popular tax filing software in the US.
- **QuickBooks:** accounting software for small businesses, covering bookkeeping, invoicing, payroll, and payments.
- **Credit Karma:** free credit scores and personal finance recommendations (acquired in 2020).
- **Mailchimp:** email marketing for small businesses (acquired in 2021), plus Intuit Assist, an AI assistant across its products.

**Business model:** Subscriptions (QuickBooks), per-filing fees (TurboTax), and referral revenue from financial products recommended on Credit Karma.

**Background:** Founded in 1983, headquartered in Mountain View, California. Competitors: H&R Block (taxes), Xero, FreshBooks, and Sage (accounting).

## Stripe

Stripe is a **payments and financial infrastructure company** that lets businesses accept payments online and manage money movement through simple developer APIs.

**Main things it does:**
- **Payments:** accept cards, wallets (Apple Pay, Google Pay), and local payment methods worldwide with a few lines of code, or through prebuilt **Stripe Checkout** pages.
- **Billing:** subscriptions and recurring payments, widely used by SaaS companies.
- **Connect:** payments for platforms and marketplaces (like Shopify, Lyft, or DoorDash) that need to pay out to many sellers or drivers.
- **More financial tools:** Radar (fraud detection), Tax, Terminal (in-person card readers), Issuing (creating cards), Treasury (banking features), Atlas (incorporating startups), and stablecoin payments through its acquisition of Bridge.

**Business model:** Mostly a fee per transaction (a percentage plus a small fixed amount per charge), plus fees for its add-on products.

**Background:** Founded in 2010 by Irish brothers Patrick and John Collison, headquartered in San Francisco and Dublin, and still **private** (one of the most valuable private tech companies). Famous for its **developer-friendly APIs and documentation**, which became the gold standard for API design. Competitors: Adyen, PayPal (Braintree), Block (Square), and Checkout.com.

## Twilio

Twilio is a **communications platform** that gives developers **APIs to send texts, make calls, and send emails** from their apps.

**Main things it does:**
- **Messaging and voice APIs:** SMS, WhatsApp, and phone calls built into apps (like Uber texting you that your driver has arrived).
- **SendGrid:** transactional and marketing email.
- **Verify:** one-time passcodes and two-factor authentication.
- **Segment:** a customer data platform that unifies user data for personalization.

**Business model:** Mostly usage-based. Customers pay per message, call minute, or email sent.

**Background:** Founded in 2008, headquartered in San Francisco, public since 2016. Competitors: Vonage, Sinch, MessageBird (Bird), Plivo, and AWS's communication services.
