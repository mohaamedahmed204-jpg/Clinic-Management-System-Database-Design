# 🏥 Clinic Management System Database Design (P1-Clinic)

![Database Status](https://img.shields.io/badge/Database-SQL_Server-blue?style=for-the-badge&logo=microsoftsqlserver)
![Design Tool](https://img.shields.io/badge/Design_Tool-Draw.io-orange?style=for-the-badge&logo=diagrams.net)
![Architecture](https://img.shields.io/badge/Architecture-Relational_Model-green?style=for-the-badge)

A comprehensive, scalable, and fully-normalized Relational Database Management System (RDBMS) designed using **Draw.io** for a modern **Clinic Management System (P1-Clinic)**. 

This repository contains the complete Entity-Relationship Diagram (ERD), relational schema, and a pre-populated Microsoft SQL Server database backup (`P1-Clinic.bak`) for testing and verification.

---

## 📌 Table of Contents
- [Overview](#-overview)
- [Core Operations](#-core-operations)
- [Key Concepts Demonstrated](#-key-concepts-demonstrated)
- [Architecture & Design](#-architecture--design)
- [Technologies & Tools](#-technologies--tools)
- [How to Use & Test](#-how-to-use--test)

---

## 🌟 Overview

The **P1-Clinic Database System** is engineered to streamline healthcare and clinical workflows, seamlessly integrating medical, administrative, and financial operations. 

It provides a robust data architecture for managing patient records, medical appointments, doctor schedules, clinical diagnoses, prescriptions, and billing, ensuring data integrity, security, and high performance for multi-user environments.

---

## ⚙️ Core Operations

The database design encapsulates the complete lifecycle of a clinical environment through the following core operations:

### 1. 🩺 Patient Management & Medical History
* **Patient Registration:** Stores demographic and contact details.
* **Medical Profile:** Tracks medical history, allergies, chronic conditions, and blood type.

### 2. 📅 Appointment Scheduling & Queueing
* **Booking System:** Manages appointment slots, statuses (Scheduled, Completed, Canceled, No-Show), and visit types.
* **Doctor Availability:** Tracks shift schedules, working hours, and doctor specializations.

### 3. 📝 Clinical Consultations & Diagnoses
* **Electronic Health Records (EHR):** Stores doctor notes, symptoms, and diagnoses for each visit.
* **Prescription Management:** Links diagnoses with prescribed medications, dosages, and instructions.

### 4. 💳 Financials, Billing & Invoicing
* **Billing System:** Generates invoices for consultations, procedures, and tests.
* **Payment Tracking:** Supports multiple payment methods (Cash, Card, Insurance) and tracks payment statuses (Paid, Pending, Refunded).

### 5. 🏥 Staff, Roles & Access Control
* **Staff Profiles:** Manages doctors, nurses, and administrative personnel.
* **Departmental Hierarchy:** Assigns doctors and staff to specific medical departments.

---

## 💡 Key Concepts Demonstrated

This database model showcases advanced database engineering and data modeling principles:

* **3rd Normal Form (3NF) Compliance:** Eliminates data redundancy, update anomalies, and ensures data integrity.
* **Referential Integrity & Constraints:** Enforces strict Foreign Key relations, `CHECK` constraints, `UNIQUE` keys, and `DEFAULT` values.
* **Scalable Junction Tables:** Implements M:N (Many-to-Many) relationships efficiently (e.g., Appointments ↔ Prescriptions/Medications).
* **Auditability & Traceability:** Uses created/updated timestamps for tracking data changes.
* **Optimized Data Types:** Selects precise SQL Server data types for memory optimization and query performance.

---

## 🏗️ Architecture & Design

The system adheres to an **Entity-Relationship Model (ERM)** comprising the following core entities:

    
    [ Patients ] <── (1:N) ── [ Appointments ] ── (N:1) ──> [ Doctors ]
        │                             │
      (1:N)                         (N:1)
        ▼                             ▼
    [ Diagnoses ]               [ Payments ]
        │
      (1:N)
        ▼
    [ Prescriptions ] ── (N:1) ──> [ Medications ]

---

### Key Tables & Relationships:
* **`Patients`**: Central entity containing demographic data.
* **`Doctors` & `Departments`**: Classifies medical professionals and their specialties.
* **`Appointments`**: Bridge entity linking `Patients` and `Doctors` with timestamped visit states.
* **`Diagnoses` & `Prescriptions`**: Captures clinical outcomes and connects directly to `Medications`.
* **`Invoices` & `Payments`**: Handles all financial transactions and links to `Appointments`.

---

## 🛠️ Technologies & Tools

* **Diagramming & Modeling:** [Draw.io](https://app.diagrams.net/) (Diagram files included).
* **Database Engine:** Microsoft SQL Server (RDBMS).
* **Language:** T-SQL (Transact-SQL).
* **Version Control:** Git & GitHub.

---

## 🚀 How to Use & Test

Restore the Database (MS SQL Server):

### 1 Open SQL Server Management Studio (SSMS).

* Right-click Databases -> Restore Database...

* Select **Device** and locate the provided **P1-Clinic.bak** file.

* Click OK to restore and test SQL queries/schema.

### 2 Open System Diagram:

* Open **Draw.io** or app.diagrams.net.

* Import the provided **.drawio** file to view or edit the ERD.

---

