# SAPS Case Accountability & Transparency System (SCATS)

---

## Group Members
- **Jodeane Kyle Bee** – 202408335
- **Kabelo George Sethunya** – 202424816
- **Kabelo Solomon Maphalla** – 202451685
- **Kamogelo Angela Macena** – 202424481

---

#  Introduction

Crime leaves a mark far beyond the moment it occurs. Every year, millions of South Africans experience the trauma of crime. They report incidents to the police, receive a case number, and are left in silence. Weeks pass, months pass, sometimes even years, without updates or clarity on the progress of their case. For victims of gender-based violence, murder, or property crime, this uncertainty is not just frustrating — it can be devastating.

While law enforcement processes millions of criminal cases annually, many victims are left waiting for answers they may never receive. Without structured visibility or meaningful communication, the aftermath of crime becomes an additional burden, eroding trust in institutions designed to protect citizens.

This project arises from the urgent need to understand and address these systemic challenges, focusing on the intersection of investigative efficiency, transparency, and the lived experience of crime victims.

---

# Problem Statement

South Africa records a high volume of reported criminal cases each year, placing significant strain on investigative and administrative systems within SAPS. Although cases are registered through the Case Administration System (CAS), victims have no structured digital mechanism to monitor the progress of their cases without physically visiting a police station or contacting the investigating officer.

## Operational Limitations

- **Lack of Victim Visibility**  
  Victims receive no notification once a case is opened, and there is no online mechanism to securely track case status.

- **Unmonitored Case Stagnation**  
  Dockets remain inactive without supervisory awareness, contributing to investigation backlogs.

- **Silent Case Closures**  
  Cases may be closed due to insufficient evidence without communication being sent to victims.

- **Paper-Based Dependency**  
  Heavy reliance on physical SAPS 3M dockets makes records vulnerable to loss, damage, or theft.

- **Inefficient Inter-Station Transfers**  
  Case transfers rely on manual documentation (fax, physical documents) instead of verified digital tracking.

---

#  Aim and Objectives

The primary aim of SCATS is to create an independent web-based platform focused on enforcing accountability and transparency. The platform empowers victims to monitor their case dockets online, communicate with investigating officers, and submit formal complaints. At the same time, it strengthens investigative accountability through automated monitoring and structured escalation mechanisms.

## Specific Objectives

- Reduce the need for victims to physically visit police stations by providing a real-time case tracking portal using a CAS number and ID number.
- Enable detectives to securely upload written statements and supporting docket documentation.
- Implement a messaging platform allowing authenticated communication between officers and complainants.
- Deploy an automated case stall detection mechanism to monitor inactive investigations.
- Provide a structured platform for complainants to submit feedback and complaints to supervisory officials.
- Maintain a cryptographically timestamped and immutable audit trail of all system actions and case events.

---

#  Proposed Solution: System Features

SCATS proposes a digital architecture designed to complement existing SAPS procedures while improving transparency and operational accountability.

1. **Real-Time Case Lifecycle Display**  
   Displays investigation stages such as `REPORTED`, `ASSIGNED`, `UNDER INVESTIGATION`, `REFERRED TO NPA`, and `COURT PROCESSING`.

2. **Embedded Messaging System**  
   Allows authenticated communication between complainants and detectives, including timestamps and read receipts.

3. **Automated Stall Detection**  
   Monitors case activity and flags inactive investigations based on predefined thresholds.

4. **Complaint Routing Engine**  
   Enables victims to submit formal concerns which are routed directly to station commanders.

5. **Detective Profile Viewing**  
   Allows citizens to view professional information about the detective assigned to their case.

---

#  System Architecture

SCATS follows a **three-tier architecture model**, separating user interfaces, application logic, and data storage to ensure security, scalability, and maintainability.

---

# Presentation Layer (User Interface)

The Presentation Layer is the primary interaction point between users and the system. It collects user input and presents system information in an accessible format.

### Citizen Public Portal
Allows complainants to securely access their case using their **Case Reference Number (CRN)** and **ID number** to:

- Track case status
- View detective information
- Book appointments
- Receive notifications
- Submit feedback or complaints

### Investigating Officer Portal
Enables detectives to:

- Manage assigned cases
- Record investigation updates
- Upload evidence and statements
- Control case progression

### Command & Management Dashboard
Provides supervisors with:

- Real-time case monitoring
- Stagnation alerts
- Investigation progress tracking
- Station performance analytics

### Administrator Interface
Allows administrators to:

- Manage users
- Configure roles and permissions
- Monitor system performance

---

# Application Layer (Business Logic Layer)

The Application Layer manages system functionality by processing requests from the Presentation Layer and applying operational rules governing criminal case management.

System services are grouped into the following modules:

## Security & Access Control

Ensures secure system usage through authentication and authorization.

- Role-based authentication
- Secure login verification
- Role-based access restrictions
- POPIA-compliant data visibility control
- Protection of sensitive investigation information

## Case Lifecycle Management

Manages the progression of a criminal case from registration to closure.

- Case Reference Number generation
- Case registration
- Detective assignment
- Investigation stage management
- Evidence uploads
- Case progression enforcement
- Digital archiving of closed cases

## Notification & Communication

Facilitates automated communication between SAPS and citizens.

- SMS confirmation after case registration
- Status change notifications
- Investigation update alerts
- Communication logging for audit purposes

## Audit & Accountability

Maintains tamper-proof records of investigation activity.

- Digital audit trail generation
- Timestamped activity logs
- Case closure justification enforcement
- Officer accountability tracking
- Read-only archival of closed cases

## Digital Handoff & Workflow Control

Ensures verified movement of dockets between officials.

- Automated CAS handoff verification
- Digital confirmation of docket receipt
- Mandatory workflow validation
- Prevention of unauthorized case movement
- Secure inter-station case transfers

---

# Data Layer (Database Layer)

The Data Layer stores and manages all system data required for investigation tracking and accountability auditing.

### The database stores:

- Criminal case and docket records
- User identities and access roles
- Investigation updates and status history
- Audit logs and timestamps
- Case transfer records
- Citizen feedback and complaints
- Archived cases
- Performance and workload metrics

The system prevents deletion of case records. Instead, cases transition through defined status stages and are archived after closure to preserve historical accountability.

---

# External System Integration

SCATS integrates with existing justice-sector systems to improve coordination:

- **Case Administration System (CAS)** – case registration validation
- **e-Docket System** – digital document storage
- **Integrated Justice System (IJS)** – interdepartmental data sharing
- **SMS Gateway** – citizen notifications
- **Government Cloud Infrastructure** – secure hosting and backups

---

# Component Interaction Flow

1. Users interact with the system through role-specific interfaces in the **Presentation Layer**.
2. Requests are transmitted to the **Application Layer** via secure APIs.
3. The **Security Module** verifies user identity and permissions.
4. The appropriate **business logic module** processes the request.
5. Approved operations retrieve or store data in the **Data Layer**.
6. Notification and monitoring services are triggered when required.
7. Results are returned to the user interface and alerts are dispatched via the **SMS Gateway**.

---

# Stakeholders

- **Citizens / Complainants**  
  Track case status, receive updates, and submit feedback.

- **Investigating Officers (Detectives)**  
  Manage investigations, upload evidence, and record case progress.

- **CSC Commanders**  
  Verify docket completeness and oversee case registration.

- **Station Commanders**  
  Monitor investigations and respond to escalated cases.

---

*Developed for the Capstone Project.*

*Section 195 of the Constitution of the Republic of South Africa (1996) states that public administration must be accountable, transparent, and responsive. SCATS seeks to support these principles through digital accountability mechanisms.*
