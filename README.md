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
```

---

## Core Files

### validation/validation.py
Builds the Tkinter GUI, handles menu actions, loads the selected LoB, displays validation options, and triggers validation or analysis.

### validation/validation_main.py
Handles execution logic:
- loads configs  
- connects to Teradata and Snowflake  
- processes validation jobs  
- writes outputs  

### validation/validation_transform.py
Handles:
- database connections  
- config/property loading  
- helper functions  

### validation/validation_analysis.py
Generates reports and performs analysis on validation results.

### configs.validation
Main configuration file containing:
- database credentials  
- logging/output directories  
- current LoB  
- system settings  

### _cargo/
Stores validation configuration CSV files.

---

## Validation Modes

### Table Size / Type
- configs.dataType.csv  
- configs.dataSize.csv  
- configs.listFutureDate.csv  
- configs.compareFutureDate.csv  

### Historical Validation
- configs.debug.csv  
- configs.histCount.csv  
- configs.histContent.csv  
- configs.allTables.csv  

### Incremental Validation
- configs.iterations.csv  
- configs.iteration1.csv  
- configs.iteration2.csv  
- configs.iteration3.csv  
- configs.iteration45.csv  

---

## How the Application Works

1. Launch GUI  
2. Select validation type  
3. Choose config file  
4. Click Submit  
5. System:
   - loads config  
   - connects to databases  
   - executes validation jobs  
6. Outputs are generated  

---

## Output Files

```
TMD_<LOB>_<ValidationType>_validation_<timestamp>.txt
TMD_<LOB>_<ValidationType>_Report_<timestamp>.csv
```

---

## Installation

### Clone repository
```bash
git clone <your-repo-url>
cd ac_validation
```

### Install dependencies
```bash
pip install -r requirements.txt
```

---

## Running the Project

### Python
```bash
python validation/validation.py
```

### Windows Batch
```bash
runval.bat
```

---

## Configuration

Edit:
```
configs.validation
```

Ensure:
- credentials are correct  
- output folders exist  
- LoB configs are present  

---

## GUI Overview

- Validation Assistant menu  
- Help menu  
- LoB display  
- radio buttons for validation type  
- config listbox  
- Analysis / Submit / Cancel buttons  

---

## Typical Workflow

1. Open app  
2. Verify LoB  
3. Select validation type  
4. Pick config file  
5. Click Submit  
6. Review outputs  
7. Run Analysis if needed  

---

## Notes

- Built using Tkinter  
- Designed for Teradata → Snowflake validation  
- Windows-oriented setup  

---

## Future Improvements

- Web UI  
- Parallel processing  
- Better error handling  
- CI/CD integration  
- Visualization dashboard  

---

## Author

Developed for internal data validation workflows.
