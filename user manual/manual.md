
# User Manual – Insp3ct++ (Executable Version Only)

---

## 1. Introduction

### Purpose of the Tool
Insp3ct++ is a lightweight system inspection utility designed to gather and present detailed hardware and system-level information in a simple TXT report format.

### Key Functionalities
- Collects system, CPU, memory, disk, USB, and network details.
- Generates human-readable reports in `.txt` format.
- Designed for offline analysis or internal audits.

### Intended Users
- Cybersecurity interns and professionals
- System administrators
- Digital forensic analysts
- Students and researchers in system-level computing

---

## 2. System Requirements

### Hardware Requirements
- Minimum 1 GHz processor
- At least 512 MB RAM
- 20 MB free disk space

### Operating System Support
- Windows 10 and above (64-bit)

### Software/Library Dependencies
- Microsoft Visual C++ Redistributable (if compiled with dependencies)
- Admin rights for full data capture (recommended)

---

## 3. Folder & File Structure

### Executable Directory Layout
Insp3ct++/
├── Insp3ct++.exe
├── run_insp3ct.bat (optional)
├── reports/
│ └── <timestamp>_system_report.txt
└── logs/ (optional)

yaml
Copy
Edit

### Output File Naming Convention
- Format: `YYYYMMDD_HHMMSS_system_report.txt`

### Temporary/Log Files
- `logs/error_log.txt` for any runtime issues (if logging is enabled)

---

## 4. Installation Guide

### Downloading and Extracting the Tool
- Download the zipped bundle from the official source.
- Extract it to your preferred location (e.g., `C:\Insp3ct++`).

### Placement of Executable
- Ensure `Insp3ct++.exe` stays in the same directory as the batch file and any required dependencies.

### Running with Admin Rights (if needed)
- Right-click `Insp3ct++.exe` → *Run as administrator*

---

## 5. Launching the Tool

### Double-click Execution
- Simply double-click on `Insp3ct++.exe` to start.

### Using a .bat File (Optional)
- Run `run_insp3ct.bat` to automate execution (useful for shortcuts or scripting).

### What Happens During Execution
- System info is collected.
- A report is generated and saved.
- The report opens automatically in Notepad.

---

## 6. Report Generation

### Format of Report (TXT)
- Plaintext `.txt` file containing structured system data.

### Location of Saved Report
- Inside the `reports/` folder within the executable directory.

### Timestamp Inclusion
- Filename includes timestamp for easy identification.

### Automatic Opening in Notepad
- After execution, the report auto-opens for review.

---

## 7. Understanding the Output

### Overview of Report Sections:
- **System Info:** Hostname, OS version, architecture.
- **CPU Info:** Processor name, cores, logical processors.
- **Disk Info:** Drive letters, sizes, file systems.
- **Network Info:** IP address, MAC address, connection status.
- **Memory Info:** Total physical memory, available memory.
- **USB Devices Info:** List of currently connected USB devices.

### Reading and Interpreting Data
- Structured with clear headings.
- Ideal for documentation, troubleshooting, or system auditing.

---

## 8. Troubleshooting

### Common Errors and Fixes
- **App not launching:** Ensure all files are extracted correctly.
- **Report not generated:** Check if the app has write permissions.

### Permissions Issues
- Run the tool as administrator for full access to system info.

### Missing DLLs or Runtime Libraries
- Install the correct version of Microsoft Visual C++ Redistributable.

---

## 9. Limitations & Notes

- Only supported on **Windows OS** (no Mac/Linux support).
- **Admin access** improves accuracy and completeness of data.
- No **online dashboard** or **cloud sync** in this version.

---










