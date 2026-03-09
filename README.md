# Crime Management System

## Abstract
The Crime Management System is a web-based application designed to help law enforcement agencies manage crime-related information efficiently. The system allows citizens to register complaints or FIRs online, while police officers can manage investigations, maintain criminal records, and track case progress. The platform aims to improve transparency, reduce manual paperwork, and ensure faster communication between citizens and police departments.

This system includes modules for complaint registration, case management, criminal record maintenance, missing person tracking, stolen property management, evidence storage, and court/legal information tracking. The application provides a centralized database that helps authorities store and retrieve crime-related information easily while ensuring secure access to authorized users.

---

# Project Objectives
- To digitize the crime reporting and management process.
- To allow citizens to register complaints online.
- To help police track investigations and case progress.
- To maintain centralized criminal and evidence records.
- To provide reports and analytics for crime analysis.

---

# System Modules

## 1. User Management
Manages system users including administrators, police officers, and citizens. It handles account creation, authentication, and role-based access control.

## 2. Citizen Registration & Login
Allows citizens to register on the system, log in securely, and manage their personal profiles.

## 3. Complaint / FIR Registration
Citizens can submit complaints or FIRs online by providing details such as description, location, and supporting documents.

## 4. Case Management
Police officers can create and update cases based on complaints and track investigation progress.

## 5. Criminal Records Management
Maintains a database of criminals including their personal details and past crime records.

## 6. Evidence Management
Stores and tracks evidence related to investigations such as documents, images, or videos.

## 7. Police Staff Management
Manages police officer details including badge number, rank, department, and station.

## 8. Missing Persons Management
Records reports of missing persons and helps authorities track updates regarding the case.

## 9. Stolen Property / Vehicle Management
Stores information about stolen property or vehicles reported by citizens.

## 10. Case Assignment
Allows senior officers to assign cases to investigating officers.

## 11. Court / Legal Management
Stores court hearing dates, legal documents, and verdict details related to cases.

## 12. Reports & Analytics
Generates crime reports and statistics based on location, time, or type of crime.

## 13. Notifications & Alerts
Sends updates to citizens and police officers about case progress and system activities.

## 14. Search Module
Allows users to search for complaints, criminals, cases, and records easily.

## 15. Dashboard Module
Provides an overview of system activity including recent complaints, active cases, and statistics.

---

# Database Schema

## Users
| Field | Type | Description |
|------|------|-------------|
| user_id | INT | Primary key |
| name | VARCHAR | User full name |
| email | VARCHAR | Unique email |
| password | VARCHAR | Encrypted password |
| phone | VARCHAR | Contact number |
| role | ENUM | ADMIN, POLICE, CITIZEN |
| created_at | TIMESTAMP | Account creation time |

## Citizens
| Field | Type |
|------|------|
| citizen_id | INT (PK) |
| user_id | INT (FK) |
| address | TEXT |
| dob | DATE |
| gender | VARCHAR |

## Police Officers
| Field | Type |
|------|------|
| officer_id | INT (PK) |
| user_id | INT (FK) |
| badge_number | VARCHAR |
| rank | VARCHAR |
| station | VARCHAR |

## Complaints
| Field | Type |
|------|------|
| complaint_id | INT (PK) |
| citizen_id | INT (FK) |
| title | VARCHAR |
| description | TEXT |
| location | VARCHAR |
| complaint_date | DATE |
| status | VARCHAR |

## Cases
| Field | Type |
|------|------|
| case_id | INT (PK) |
| complaint_id | INT (FK) |
| case_status | VARCHAR |
| opened_date | DATE |
| closed_date | DATE |

## Case Assignments
| Field | Type |
|------|------|
| assignment_id | INT (PK) |
| case_id | INT (FK) |
| officer_id | INT (FK) |
| assigned_date | DATE |

## Evidence
| Field | Type |
|------|------|
| evidence_id | INT (PK) |
| case_id | INT (FK) |
| evidence_type | VARCHAR |
| description | TEXT |
| file_path | VARCHAR |
| collected_date | DATE |

## Criminals
| Field | Type |
|------|------|
| criminal_id | INT (PK) |
| name | VARCHAR |
| age | INT |
| gender | VARCHAR |
| address | TEXT |
| crime_history | TEXT |

---

# Technology Stack

## Frontend
- React.js
- HTML
- CSS
- JavaScript

## Backend
- Spring Boot
- REST APIs

## Database
- MySQL

## Tools
- Git
- IntelliJ IDEA / VS Code
- Postman for API testing

---

# System Architecture
The system follows a **three-tier architecture**:

1. **Presentation Layer**
   - User interface built using React.

2. **Application Layer**
   - Backend services using Spring Boot.

3. **Data Layer**
   - MySQL database storing all system data.

---

# Installation Guide

## 1. Clone Repository