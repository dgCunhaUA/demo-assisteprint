# 📌 Assisteprint Portal

_Business management platform for printing services_

---

## 🌐 Demo

You can explore the demo environment below.

-   🚀 **Live Demo**: [demo.assisteprint.com](https://demo.assisteprint.com)
-   🔑 **Demo Access**:
    -   Admin:
        -   demo@assisteprint.com
        -   assisteprint-demo-password
    -   Staff:
        -   ...
        -   ...
    -   User
        -   john@example.com
        -   ...

⚠️ _Note: Some operations are disabled in the demo version. For questions or feedback, feel free to reach out._

---

## 🚀 Overview

The **Assisteprint Portal** is a web platform built to help streamline company operations.  
It centralizes contract management, copy counts, invoicing, and reporting — reducing manual work and improving efficiency.

---

## ✨ Key Aspects

-   🔐 **Role-based access control (RBAC)** — secure and granular permissions (admin, staff, user)
-   💰 **Sage integration** — third party integration for automated invoicing to reduce errors and save time
-   📊 **Dashboards & reports** — real-time insights into contracts, machines, and profitability
-   📋 **Ticket Board** — Jira style ticket board for management of staff

---

## 🛠️ Tech Stack

-   **Frontend**: React / RTK Query / Chakra UI
-   **Backend**: Node.js / Express
-   **Database**: PostgreSQL
-   **Other**: Docker / Nginx / OpenSearch / cPanel

---

## 🏗️ Architecture

```mermaid

flowchart TB
  subgraph User["User"]
      USER["User Browser"]
  end

  subgraph Cloud["cPanel Cloud"]
      CP["cPanel (Web Hosting / Email)"]
  end

  subgraph ProdVM["Production VM"]
      subgraph Docker["Docker Containers"]
          FE["Frontend (React.js)"]
          BE["Backend (Node.js)"]
          DB["PostgreSQL"]
          OS["OpenSearch"]
      end
  end

  subgraph HyperV["Hyper-V Host"]
      NGINX["Nginx Reverse Proxy VM"]
      ProdVM
      Demo["Demo & Staging VM"]
  end

  subgraph OnPrem["On-Premise Infrastructure"]
      ISP["ISP Connection"]
      RT["MikroTik Router"]
      HyperV
  end

  NGINX --> ProdVM
  NGINX --> Demo

  USER --> CP
  CP <--> ISP
  ISP --> RT
  RT --> NGINX

```

## 👤 Author

**Diogo Cunha**

-   📧 diocunha@outlook.pt
-   💼 [LinkedIn](https://www.linkedin.com/in/diogo-cunha-a86185177/)
