# Workflow of Insp3ct++ Audit Tool (Web + Client System)

---

## 1. Initial Setup (One-Time)

- **XAMPP Setup:** Admin installs and configures XAMPP (Apache, MySQL, PHP) on a central server machine.
- **Database Creation:** Admin creates a MySQL database (e.g., `audit_db`) with key tables:
  - `users` – Stores login credentials and roles.
  - `logins` – Records each login with timestamp and client details.
  - `system_logs` – Stores system audit reports in XML format.

---

## 2. User Login Flow (Intranet Access)

- Users navigate to the internal audit tool portal:
http://<SERVER_IP>/audit_tool/

- PHP-based login page handles authentication:
- **Admin Role:** Full access to dashboard, run audits, view all reports.
- **Normal Users:** Limited access to personal machine logs or summaries.

---

##  3. Triggering the Audit

- Admin (or authorized user) initiates an audit:
- From the web dashboard, selects a machine to audit.
- Alternatively, executes `Insp3ct++.exe` directly on the client machine.
- The client tool (`Insp3ct++.exe`):
- Gathers system information (CPU, Memory, Disk, USB, etc.)
- Exports the data as an XML file.
- Sends the XML data to the server via HTTP POST to `upload.php`.

---

## 4. Recording & Storing Data

- `upload.php` (server-side script):
- Accepts XML data and machine/user identifiers.
- Inserts a new entry into the `logins` table (with timestamp).
- Saves the XML data to the `system_logs` table (as raw XML or a file reference).

---

##  5. Admin Dashboard Functionality

- Admin logs into the portal and sees:
- Summary of all client machines.
- Last audit date per machine.
- Number of logins per user or machine (e.g., monthly stats).
- Download links for XML reports.
- Overview of:
  - CPU usage trends
  - Missing machines
  - System anomalies (if enabled)

---

##  6. Anomaly Monitoring (Optional Phase)

- Admin can analyze each machine for:
- Sudden CPU usage changes
- New USB devices
- Login pattern deviations
- Export options:
- Download audit report in XML or JSON format.

---

##  Summary Flow Diagram (Textual)

[ User on LAN ]

|
v
[ Login Page (PHP) ]

|

+--> Successful login
|

[ Admin Dashboard ] <------------------------------+
| |

+--> Run audit on Machine A |

| |
v |

[ Insp3ct++ client .exe ] |
| |

→ collects data → XML → HTTP POST → Upload.php |
| |

+----------- confirms receipt and store in DB
|

v

[ Data saved: logins/system_logs ]
|
v

[ Admin views via web dashboard ]



---

## Summary

- The **web portal** handles user login, dashboard display, and server-side storage.
- The **client executable** collects system information and securely sends it to the server.
- The **database** acts as the backbone for logging and storing data for audits.
- Admins can monitor systems, export reports, and detect anomalies from one unified interface.
