# **Technology Stack**

GKMIT_INSIDE is built using modern web technologies to ensure performance, scalability, and maintainability.

<!-- <div style="display: flex; justify-content: start; align-items: center; gap: 30px;">
  <img src="https://cdn.worldvectorlogo.com/logos/react-2.svg" alt="React" width="75">
  <img src="https://cdn.worldvectorlogo.com/logos/nodejs-icon.svg" alt="Node.js" width="75">
  <img src="https://cdn.worldvectorlogo.com/logos/express-109.svg" alt="Express.js" width="100" style="background-color: white; padding: 0.2rem">
  <img src="https://cdn.worldvectorlogo.com/logos/mongodb-icon-1.svg" alt="MongoDB" width="75">
  <img src="https://cdn.worldvectorlogo.com/logos/tailwindcss.svg" alt="TailwindCSS" width="75">
</div> -->

<div style="display: flex; justify-content: center; align-items: center; flex-wrap: wrap; gap: 30px;">

  <!-- ReactJS -->
  <img src="https://cdn.worldvectorlogo.com/logos/react-2.svg" alt="ReactJS" width="90">

  <!-- TailwindCSS -->
  <img src="https://cdn.worldvectorlogo.com/logos/tailwindcss.svg" alt="TailwindCSS" width="90">

  <!-- Shadcn UI -->
  <img src="https://avatars.githubusercontent.com/u/139895814?s=200&v=4" alt="Shadcn UI" width="90" style="border-radius: 10px;">

  <!-- Node.js -->
  <img src="https://cdn.worldvectorlogo.com/logos/nodejs-icon.svg" alt="Node.js" width="90">

  <!-- Express.js -->
  <span style="display:inline-flex;align-items:center;justify-content:center;width:85px;height:85px;background:white;padding:6px;border-radius:10px;box-shadow:0 1px 2px rgba(0,0,0,0.08);">
    <img src="https://cdn.worldvectorlogo.com/logos/express-109.svg" alt="Express.js" width="100">
  </span>

  <!-- MongoDB -->
  <img src="https://cdn.worldvectorlogo.com/logos/mongodb-icon-1.svg" alt="MongoDB" width="90">

  <!-- Vercel -->
  <img style="display:inline-flex;align-items:center;justify-content:center;width:85px;height:85px;background:white;padding:6px;border-radius:10px;box-shadow:0 1px 2px rgba(0,0,0,0.08);" src="https://cdn.worldvectorlogo.com/logos/vercel.svg" alt="Vercel" width="100">
</div>

## **Stack Overview (Stable Versions)**

| **Category**             | **Technology** | **Stable Version** | **Purpose**                      | **Version (LTS)**    |
| ------------------------ | -------------- | ------------------ | -------------------------------- | -------------------- |
| **Frontend Framework**   | ReactJS        | v19.2.0            | Core Library / Fast UI Rendering | ✅ LTS               |
| **Build Tool**           | Vite           | v7.2               | Next-gen Frontend Tooling        | ✅ LTS               |
| **State Management**     | Context API    | N/A (Core)         | Global State Management          | ✅ Included in React |
| **Styling Framework**    | Tailwind CSS   | v4.1.13            | Utility-first CSS Styling        | ✅ Stable            |
| **UI Component Library** | Shadcn/UI      | v0.9.5             | Accessible & Customizable UI     | ✅ Stable            |
| **Backend Runtime**      | Node.js        | v24.x              | Server-side Logic Runtime        | ✅ LTS               |
| **Backend Framework**    | Express.js     | v5.1.0             | API Routes and Middleware Logic  | ✅ Stable            |
| **Authentication**       | JWT            | v9.0.2             | Token-based Security             | ✅ Stable            |
| **Database**             | MongoDB        | v8.0               | NoSQL Document Database          | ✅ LTS               |
| **Frontend Deployment**  | Vercel         | N/A (Platform)     | Frontend Hosting Platform        | ✅ Managed           |
| **Backend Deployment**   | Render         | N/A (Platform)     | Backend Hosting Platform         | ✅ Managed           |

---

## System Architecture Diagram

```mermaid
graph LR
    subgraph "Client Layer"
    A[React + Context API + TailwindCSS + Shadcn]
    end

    subgraph "Application Layer"
    B[Node.js + Express + JWT]
    end

    subgraph "Database Layer"
    C[MongoDB]
    end

    A -->|HTTPS/REST API| B
    B -->|MongoDB Driver| C
```

---

### **Summary**

This technology stack is built on **modern, long-term stable (LTS)** releases ensuring security, performance, and maintainability.

- **Frontend:** React, Vite, Tailwind, and Shadcn/UI deliver a fast, modular, and elegant UI layer.
- **Backend:** Node.js and Express.js ensure robust, scalable API development.
- **Data Layer:** MongoDB provides flexible NoSQL storage optimized for scalability.
- **Deployment:** Vercel and Render streamline CI/CD pipelines with managed hosting for both frontend and backend.
