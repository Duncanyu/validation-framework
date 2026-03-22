# validation-framework

# Validation Framework  
### Teradata vs. Snowflake Data Validation Tool
<img width="1295" height="705" alt="validation1" src="https://github.com/user-attachments/assets/ceabf88e-1faf-4651-a45e-81ab48b936bb" />
<img width="1287" height="698" alt="validation2" src="https://github.com/user-attachments/assets/01c48ee6-1558-4e6e-9345-f14a0058e5ad" />

---

## Overview

This project is a Python-based desktop validation framework used to compare data between **Teradata** and **Snowflake**. It provides a Tkinter GUI for selecting validation modes, loading configuration files, executing validation jobs, and generating reports for analysis.

The application is intended to support data migration and validation workflows by checking whether source and target systems remain aligned across schema, size, and date-related rules.

---

## What the Project Does

The framework allows a user to:

- choose a validation category from the GUI
- select a configuration CSV file
- run validation jobs against Teradata and Snowflake
- generate validation logs and CSV reports
- run analysis on validation results
- manage Line of Business (LoB) configuration from the interface

---

## Main Features

- **Tkinter GUI** for running validations
- **Config-driven workflow** using `.validation` and `.csv` files
- **Multiple validation modes**, including:
  - table size and type validation
  - historical data validation
  - incremental data validation
  - future-date checks
- **Teradata and Snowflake connectivity**
- **Generated log files and statistic reports**
- **LoB switching support** from the application menu
- **Analysis module** for reviewing output data
- **Batch launcher** for Windows execution

---

## Project Structure

```text
ac_validation/
├── ac.gif
├── configs.validation
├── pyodbc-4.0.32-cp310-cp310-win_amd64.whl
├── requirements.txt
├── runval.bat
├── TMD UAT Validation.lnk
├── _archive/
├── _cargo/
├── validation/
│   ├── validation.py
│   ├── validation_main.py
│   ├── validation_transform.py
│   ├── validation_analysis.py
│   └── test/
│       └── test.py
