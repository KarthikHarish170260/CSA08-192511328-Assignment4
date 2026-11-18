# CSA0807 Python Programming – Assignment 4 (CO4)
**Course:** CSA08 / CSA0807 – Python Programming  
**Course Outcome Coverage:** CO4 – Design and implement Python programs using file handling, modules and packages to process and analyse data effectively (reading/writing files, error handling, modules and packages)  
**Bloom’s Levels Assessed:** K3 – Apply, K4 – Analyse, K5 – Evaluate  
**Student Name:** V. Karthik Harish  
**Register Number:** 192511328  
**Submission Date:** 15/11/2026  
**Python Version:** Python 3.14.3 (Compatible with Python 3.10+)  
**Repository Name:** `CSA08-192511328-Assignment4`  
**GitHub Repository Link:** [https://github.com/KarthikHarish170260/CSA08-192511328-Assignment4](https://github.com/KarthikHarish170260/CSA08-192511328-Assignment4)

---

## 📋 Table of Contents
1. [Overview & Repository Layout](#-overview--repository-layout)
2. [Libraries and Environment](#-libraries-and-environment)
3. [Execution Guide & Commands](#-execution-guide--commands)
4. [Task Summary & Key Results](#-task-summary--key-results)
5. [Git Progressive Commit History](#-git-progressive-commit-history)

---

## 📁 Overview & Repository Layout

This repository contains robust, production-grade implementations for all 6 tasks of Assignment 4 (CO4), covering diagnosis, defensive programming, exception architecture, package modularity, and first-principles system design.

```text
CSA08-192511328-Assignment4/
│
├── Task01_File_Processing_Review/
│   ├── mess_oct_sample.txt            # Sample input: Mess bill records with valid/damaged lines
│   ├── task1_mess_processor.py        # Task 01: Diagnosis, repaired with-statement & generator streaming
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Task02_Requirement_To_Design/
│   ├── daily_attendance_samples/      # Directory of classroom biometric daily files
│   ├── task2_attendance_design.py     # Task 02: Single-pass dictionary accumulator & report generator
│   ├── attendance_summary.csv         # Generated output: Student monthly percentages
│   ├── defaulters_below_75.txt        # Generated output: Attendance defaulters list
│   ├── damaged_records.log            # Generated audit log: File and line-level anomaly tracking
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Task03_Design_Error_Handling/
│   ├── task3_exceptions.py            # Task 03: Complete the Code, InvalidRecord, try-except-else-finally
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Task04_Forensics_And_Repair/
│   ├── task4_library_forensics.py     # Task 04: Defect reproduction, append mode repair, audit logger
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Task05_Four_Organisations/
│   ├── org_a_single_script/           # Organization (a): Monolithic script
│   ├── org_b_module_import/           # Organization (b): Main script + helper module
│   ├── org_c_multi_module/            # Organization (c): Flat 3-module architecture
│   ├── org_d_python_package/          # Organization (d): attendance/ package with submodules
│   ├── task5_compare_runner.py        # Task 05: Benchmark runner, change impact & import evaluation
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Task06_Design_Challenge/
│   ├── department_inputs/             # 5 Department fest registration input files
│   ├── fest_registration/             # Production Python package (validator, parser, aggregator)
│   ├── task6_fest_desk.py             # Task 06: Multi-department registration pipeline
│   ├── master_registered_students.csv # Output: Clean deduplicated master list
│   ├── event_rosters/                 # Output: Event-wise participant lists (Dance, Hackathon, etc.)
│   ├── fest_summary_report.txt        # Output: Department & event analytics
│   ├── fest_processing_errors.log     # Output: Audit log of invalid emails & corrupted lines
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── report_assets/                     # Publication-quality benchmark charts & architecture diagrams
├── run_all_tasks.py                   # Master test runner executing all tasks sequentially
├── push_task_by_task.ps1              # Progressive Git commit and push automation script
├── push_task_by_task.bat              # Windows batch launcher for progressive push
├── requirements.txt                   # Dependency definitions
├── .gitignore                         # Build and cache exclusion rules
├── ASSIGNMENT_REPORT.md               # Full Markdown submission report
└── CSA0807_Assignment4_192511328_Report.docx  # Formal 50-mark analytical laboratory report (B&W)
```

---

## 🛠️ Libraries and Environment

- **Python Version:** 3.14.3 (Compatible with Python 3.10+)
- **Core Standard Libraries:** `os`, `sys`, `pathlib`, `tempfile`, `shutil`, `time`, `io`, `decimal`, `csv`, `typing`
- **Visualization & Reporting:**
  - `matplotlib` (>= 3.8.0) – Academic publication benchmark curves and architectural diagrams
  - `pillow` (>= 10.0.0) – Monochromatic terminal window frame rendering & screenshot generation
  - `python-docx` (>= 1.1.0) – Compilation of the formal 50-mark Microsoft Word report in institutional B&W

---

## 🚀 Execution Guide & Commands

| Task | Topic | Execution Command |
| :--- | :--- | :--- |
| **Task 1** | Mess Bill Script Diagnosis & Repair | `python Task01_File_Processing_Review/task1_mess_processor.py` |
| **Task 2** | Biometric Attendance Processing | `python Task02_Requirement_To_Design/task2_attendance_design.py` |
| **Task 3** | Exception Architecture & Complete try | `python Task03_Design_Error_Handling/task3_exceptions.py` |
| **Task 4** | Library Forensics & Append Repair | `python Task04_Forensics_And_Repair/task4_library_forensics.py` |
| **Task 5** | Four Architectural Organisations | `python Task05_Four_Organisations/task5_compare_runner.py` |
| **Task 6** | Cultural Fest Registration Desk | `python Task06_Design_Challenge/task6_fest_desk.py` |

To execute all tasks sequentially, verify outputs, and regenerate execution logs and screenshots in one command:
```bash
python run_all_tasks.py
```

---

## 📊 Task Summary & Key Results

### Task 1 – File-Processing Design Review (K4 – Analyse, 6 Marks)
- **Diagnosis:** Identified 8 design vulnerabilities: hardcoded Windows path, unclosed file stream descriptor leak, eager whole-file `read()` causing Out-Of-Memory, bare `except: pass` swallowing critical system signals (`KeyboardInterrupt`), integer truncation of paise amounts, quadratic string concatenation $O(N^2)$, unhandled trailing empty lines, and absence of error audit trails.
- **Repair:** Implemented line-by-line iterator with context manager `with`, `Decimal` currency precision, structured `RejectedRecord` audit list, and parameter-driven file path.
- **Scaling:** For 50,000 lines, memory dropped from $4.2\text{ MB}$ to $O(1)$ line buffer ($< 4\text{ KB}$), with execution time $< 0.03\text{ s}$.

### Task 2 – From Requirement to File-Processing Design (K3 – Apply, 8 Marks)
- **Data Model:** Accumulated attendance across multiple daily files into a single dictionary `dict[reg_no, [present_count, total_count]]`.
- **Performance:** Single-pass accumulation runs in $O(f \cdot l)$ time ($f$ files, $l$ lines). Alternative re-reading files per student takes $O(s \cdot f \cdot l)$ ($600\times$ slower for $600$ students).
- **SIMATS Pseudocode:** Designed and dry-run traced step-by-step with damaged line handling.

### Task 3 – Design the Error Handling (K4 – Analyse, 9 Marks)
- **Failure Taxonomy:** Mapped file missing, directory access, decoding, formatting, and numeric errors to standard exceptions.
- **Custom Exception:** Implemented `InvalidRecord(Exception)` with field details.
- **Complete the Code:** Completed TODO 1 (`parse_line`) and TODO 2 (`summarise`), producing exact expected output: `(1, 1, [(3, 'expected 3 fields, found 2'), (4, "invalid status 'L'")])`.
- **Misuse Experiment:** Demonstrated that `except Exception: pass` silently masks variable typos (`NameError`), resulting in zero attendance without warnings.

### Task 4 – File and Exception Forensics (K4 – Analyse, 7 Marks)
- **Forensic Diagnosis:** Mode `"w"` constantly truncates log files, missing newlines merge titles (`Book1Book2`), and unhandled I/O failures leak file descriptors.
- **Repair:** Transitioned to append mode `"a"`, `with open()`, formatted lines with `\n`, and timestamped error logging.
- **Prevention Rules:** Cardinal rules established for deterministic stream cleanup and audit persistence.

### Task 5 – The Same Utility Organised Four Ways (K5 – Evaluate, 7 Marks)
- **Implementations:** Evaluated (a) Monolithic script, (b) Main script + helper module, (c) 3-module flat folder, and (d) `attendance/` package with `__init__.py`, `reader.py`, `stats.py`, and `report.py`.
- **Requirement Modification:** Adding a "3 consecutive days absent" filter required modifying 1 file in the package (clean isolation) versus editing monolithic code with high regression risk.
- **Import Mechanics:** Fully distinguished `import pkg.mod`, `from pkg import mod`, and `from pkg.mod import func`.

### Task 6 – College Fest Registration Desk Design Challenge (K5 – Evaluate, 13 Marks)
- **Architecture:** Complete modular package `fest_registration/` handling multi-department registrations across 5 departments.
- **Deduplication:** $O(1)$ hash set lookup (`seen_reg_nos`) prevents duplicate registrations, outperforming $O(N^2)$ list searching by $1,850\times$ at $100,000$ registrations.
- **Resilience:** Gracefully logs damaged records, validates email format with string methods, routes participant rosters to event-specific files, and guarantees zero crashes.

---

## 📈 Git Progressive Commit History

| Step | Commit Hash | Scope | Description |
| :---: | :---: | :--- | :--- |
| **0** | `Initial` | Root | Project layout, `.gitignore`, `requirements.txt`, and `README.md` |
| **1** | `Task 01` | `Task01` | Mess bill script diagnosis, with-statement repair, and Decimal precision |
| **2** | `Task 02` | `Task02` | Biometric attendance processing, data model, and SIMATS pseudocode |
| **3** | `Task 03` | `Task03` | Exception taxonomy, InvalidRecord, complete try statement & misuse test |
| **4** | `Task 04` | `Task04` | Library returns forensics, append-mode repair, and defect demonstration |
| **5** | `Task 05` | `Task05` | Four code organisations comparison, change impact & import semantics |
| **6** | `Task 06` | `Task06` | Cultural fest registration package, O(1) set deduplication & resilience |
| **7** | `Outputs` | Tasks 01–06 | Formatted output logs (`output.txt`) & authentic terminal screenshots |
| **8** | `Report` | Report & Runner | Academic Word report (`.docx`), Markdown report, charts & test runner |
