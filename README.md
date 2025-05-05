# CISA KEV Mirror

This repository contains a continuously updated mirror of the [CISA Known Exploited Vulnerabilities (KEV) catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog), available in CSV format.

Data is refreshed every **2 hours** and organized in multiple formats for easier access and analysis.

## Repository Structure

CVE data is available in the following formats:

1. **All CVEs in a single file**  
   Get all CVEs &rarr; https://github.com/lucacapacci/cisa_kev/raw/refs/heads/main/cisa_kev.csv

2. **Files grouped by year**  
   Example: get all CVEs starting with "CVE-2025-" &rarr; https://raw.githubusercontent.com/lucacapacci/cisa_kev/refs/heads/main/data_years/cisa_kev_2025.csv

3. **Files grouped by year and first digit of the CVE ID**  
   Example: get all CVEs starting with "CVE-2025-0" &rarr; https://raw.githubusercontent.com/lucacapacci/cisa_kev/refs/heads/main/data_groups/cisa_kev_2025_0.csv
   
4. **Single file per CVE**  
   Example: get CVE-2025-0108 &rarr;
   https://raw.githubusercontent.com/lucacapacci/cisa_kev/refs/heads/main/data_single/2025/CVE-2025-0108.csv

---

## Usage Examples

### Using `curl`

```bash
curl -L https://raw.githubusercontent.com/lucacapacci/cisa_kev/refs/heads/main/data_single/2025/CVE-2025-0108.csv
```

### Using Python

```python
import requests
import csv
from io import StringIO

url = 'https://raw.githubusercontent.com/lucacapacci/cisa_kev/refs/heads/main/data_single/2025/CVE-2025-0108.csv'
response = requests.get(url)
csv_file = StringIO(response.text)
reader = csv.reader(csv_file)
for row in reader:
    print(row)
```

---

## Update Frequency

Data is automatically updated every **2 hours**, providing near real-time CVE tracking.
