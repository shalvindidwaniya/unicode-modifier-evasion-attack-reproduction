# Unicode Modifier Evasion Attack Reproduction

## Paper

**Fooling Machine’s Eyes: Unicode Modifier Letter Evasion Attack**

### Authors

* Chao Gao
* Guanglu Sun
* Xin Liu
* Feiyan Liu

### Conference

Annual Computer Security Applications Conference (ACSAC), 2025

---

# Project Overview

This project reproduces the experiments presented in the research paper:

> *Fooling Machine’s Eyes: Unicode Modifier Letter Evasion Attack*

The paper investigates how Unicode modifier letters can be abused to evade machine-based detection systems while remaining visually understandable to humans.

The reproduction was performed using the official artifact provided by the authors.

---

# Research Problem

Unicode modifier letters visually resemble normal ASCII characters but are internally represented differently.

Example:

```text
password
```

Unicode modifier variant:

```text
pᵃssword
```

Humans can still interpret the modified text correctly, but security systems relying on exact string comparison may fail to detect it.

The paper studies how Windows APIs such as `CompareStringW()` process these characters and how attackers may exploit this behavior.

---

# Objectives

* Reproduce the official artifact experiments
* Execute Unicode character scanning
* Generate experimental reports
* Verify reproduced outputs
* Analyze Unicode equivalence behavior
* Study security implications of Unicode modifier evasion

---

# Artifact Components

The official artifact contains:

| Component      | Purpose                                      |
| -------------- | -------------------------------------------- |
| `analyzer.exe` | Vulnerability analysis tool                  |
| `checker.exe`  | Unicode Modifier Converter                   |
| `Report/`      | Generated experiment reports                 |
| `claims/`      | Expected outputs and reproducibility scripts |

---

# Experiments Reproduced

## 1. Character Equivalence Scanning

Executed:

```powershell
.\analyzer.exe
```

Selected:

```text
Option 4 — CompareStringW character scanning
```

Generated output:

```text
TestReport2.txt
```

---

## 2. Unicode Modifier Converter Verification

Executed:

```powershell
.\checker.exe
```

Verified Unicode modifier normalization.

Example:

```text
ᵗᵉˢᵗ → test
```

---

# Reproduction Verification

The generated report was compared against the expected artifact output using SHA256 hash verification.

Result:

✅ Exact output reproduction achieved.

---

# Example Unicode Modifier Attacks

| Original | Unicode Variant |
| -------- | --------------- |
| password | pᵃssword        |
| malware  | mᵃlwᵃre         |
| admin    | admᶦn           |
| trojan   | trᵒjᵃn          |

---

# Security Implications

The research demonstrates risks related to:

* Malware obfuscation
* Signature evasion
* Unicode spoofing
* Phishing attacks
* Security filter bypasses

---

# Environment

| Parameter        | Value                |
| ---------------- | -------------------- |
| Operating System | Windows 10/11        |
| Environment      | PowerShell + VS Code |
| Architecture     | x64                  |

---

# Commands Used

## Run Analyzer

```powershell
.\analyzer.exe
```

## Run Checker

```powershell
.\checker.exe
```

## SHA256 Verification

```powershell
Get-FileHash <file_path>
```

---

# Repository Structure

```text
/report
/ppt
/screenshots
/generated_reports
/artifact_notes
README.md
```

---

# Reproduction Status

| Task                           | Status |
| ------------------------------ | ------ |
| Artifact setup                 | ✅      |
| Analyzer execution             | ✅      |
| Character scan reproduction    | ✅      |
| Output generation              | ✅      |
| SHA256 verification            | ✅      |
| Unicode equivalence validation | ✅      |

---

# References

1. Chao Gao, Guanglu Sun, Xin Liu, and Feiyan Liu,
   *Fooling Machine’s Eyes: Unicode Modifier Letter Evasion Attack*,
   ACSAC 2025.

2. Official Zenodo Artifact provided by the authors.

3. Microsoft Documentation — `CompareStringW()` API.

4. Unicode Consortium Documentation.
