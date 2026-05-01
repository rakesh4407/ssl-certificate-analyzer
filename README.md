# 🔐 SSL Certificate Analyzer

> **Automated SSL Certificate Analysis & Lead Qualification Tool**  
> Built during **Data Science Internship** at [The SSL Lock](https://www.thessllock.com), Chennai (June – July 2025)

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Latest-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Ready-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

---

## 📌 About the Project

This tool was developed as a **real-world industry project** during my Data Science Internship at **The SSL Lock, Chennai** — one of India's leading SSL certificate providers.

The tool automates the process of extracting and analyzing SSL certificate metadata from bulk domain datasets, helping the business sales team **identify high-priority leads** based on certificate expiry timelines — replacing hours of manual work with a single automated pipeline.

---

## 🎯 Business Problem Solved

| Problem | Solution |
|---|---|
| Manual SSL checking for 1000s of domains | Automated bulk processing pipeline |
| Inconsistent certificate data formats | Multi-format parser (tuple, dict, string) |
| No visibility on expiry urgency | Days remaining calculation per domain |
| Unstructured lead data | Clean Excel report exported to Drive |

---

## ✨ Features

- ✅ **Bulk Domain Processing** — Reads domain list from Excel (.xls/.xlsx)
- ✅ **Live SSL Certificate Fetching** — Connects via Python `ssl` & `socket` libraries
- ✅ **Issuer Organization Detection** — Extracts CA name (DigiCert, Sectigo, Cloudflare etc.)
- ✅ **Wildcard Certificate Detection** — Identifies `*.domain.com` certificates
- ✅ **Expiry Timeline Calculation** — Calculates exact days remaining until expiry
- ✅ **Validity Period Detection** — Identifies 1-year vs 2-year certificates
- ✅ **Country Extraction** — Extracts country from certificate subject field
- ✅ **Multi-format Parsing** — Handles tuple, dict & string certificate formats
- ✅ **Progress Tracking** — Real-time progress bar using `tqdm`
- ✅ **Structured Excel Export** — Saves clean results to Google Drive

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Python 3.8+** | Core programming language |
| **Pandas** | Data manipulation & Excel I/O |
| **ssl** (built-in) | SSL certificate connection & extraction |
| **socket** (built-in) | TCP connection to domains |
| **re** (regex) | Certificate field parsing fallback |
| **tqdm** | Progress bar for bulk processing |
| **Google Colab** | Cloud execution environment |
| **Google Drive** | Input/output data storage |

---

## 📊 Output Fields

| Column | Description |
|---|---|
| `Domain` | Input domain name |
| `SSL_Not_Before` | Certificate issue date (DD/MM/YYYY) |
| `SSL_Not_After` | Certificate expiry date (DD/MM/YYYY) |
| `Organization_Name` | Certificate issuing organization |
| `Common_Name` | Certificate Authority (CA) name |
| `Validity_days` | Total certificate validity in days |
| `Validity_years` | 1 year or 2 years |
| `Today_date` | Date of analysis run |
| `Wild_card_Common_Name` | Wildcard CN if present (*.domain.com) |
| `days_remaining` | Days until certificate expiry |
| `Country` | Country extracted from certificate |

---

## 🚀 How to Run

### Step 1 — Clone or Open in Google Colab
```bash
git clone https://github.com/rakesh4407/ssl-certificate-analyzer.git
```
Or directly open `ssl-certificate-analyzer.ipynb` in **Google Colab**

### Step 2 — Mount Google Drive
```python
from google.colab import drive
drive.mount('/content/drive')
```

### Step 3 — Upload Domain Excel File
```
Place your domain list Excel (.xls/.xlsx) in Google Drive
Update the file path in the script:
df = pd.read_excel("drive/MyDrive/YOUR_FILE.xls")
```

### Step 4 — Run All Cells
```python
# Script processes all domains automatically
# Results saved to: drive/MyDrive/Lead_Sample_result.xlsx
```

### Step 5 — View Results
```
Open Lead_Sample_result.xlsx from Google Drive
Filter by 'days_remaining' to find urgent leads!
```

---

## 📁 Project Structure

```
ssl-certificate-analyzer/
│
├── ssl-certificate-analyzer.ipynb   # Main Jupyter notebook
├── README.md                        # Project documentation
```

---

## 🔬 How It Works

```
Input Excel (Domain List)
        ↓
For each domain:
  → Connect via socket (port 443)
  → Wrap with SSL context
  → Extract certificate (getpeercert())
  → Parse: issuer, subject, dates, CN
  → Calculate: validity days, days remaining
        ↓
Compile results into DataFrame
        ↓
Export to Excel (Google Drive)
```

---

## ⚠️ Error Handling

The tool gracefully handles:
- **Timeout errors** — 10 second connection timeout per domain
- **Invalid domains** — Returns empty fields, continues processing
- **Mixed certificate formats** — 3-method fallback parser
- **Missing fields** — Returns empty string, never crashes

---

## 📈 Impact

- 🔄 **Automated** bulk SSL certificate analysis for thousands of domains
- ⏱️ **Saved hours** of manual checking daily for the sales team
- 🎯 **Prioritized leads** by days remaining until SSL expiry
- 📊 **Structured reports** ready for immediate sales team use

---

## 👨‍💻 Author

**Rakesh G**

BCA (H) — Artificial Intelligence & Data Science  
K.R. Mangalam University, New Delhi | CGPA: 9.22/10  
Dean's Award Recipient | IBM Certified Data Scientist

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Rakesh%20G-0077B5?style=flat&logo=linkedin)](https://linkedin.com/in/rakesh-bca)
[![GitHub](https://img.shields.io/badge/GitHub-rakesh4407-181717?style=flat&logo=github)](https://github.com/rakesh4407)
[![Email](https://img.shields.io/badge/Email-rakee4407%40gmail.com-D14836?style=flat&logo=gmail)](mailto:rakee4407@gmail.com)

---

## 🏢 Internship Details

| Detail | Info |
|---|---|
| **Company** | The SSL Lock, Chennai |
| **Website** | [www.thessllock.com](https://www.thessllock.com) |
| **Domain** | Data Science |
| **Duration** | June 2025 – July 2025 |
| **Mode** | Remote |
| **Certificate** | Issued July 15, 2025 |

---

## 🏷️ Topics

`python` `ssl` `data-science` `pandas` `socket-programming` `data-analysis` `excel-automation` `google-colab` `lead-generation` `internship-project` `certificate-analysis`

---

## 📜 License

This project was developed for internship purposes at **The SSL Lock, Chennai**.  
© 2025 Rakesh G — All rights reserved.

---

⭐ **If you found this useful, please star this repository!**
