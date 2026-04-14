# API Ethics Assignment

**Submitted by:**AZAZ AHMED 

---

## Task 1 — Classify and Handle PII Fields

### Overview
The dataset contains several fields that include sensitive personal information. To ensure privacy and responsible data sharing, each field must be classified as either Direct PII or Indirect PII and handled appropriately before sharing with external parties.

---

### Field Classification and Handling

#### 1. Full Name
- **Type:** Direct PII  
- **Action:** Dropped  
- **Justification:** Full name directly identifies an individual and is not required for analysis.

---

#### 2. Email
- **Type:** Direct PII  
- **Action:** Masked  
- **Justification:** Email addresses are unique identifiers and sensitive. Masking helps retain partial information without exposing identity.

---

#### 3. Date of Birth
- **Type:** Indirect PII  
- **Action:** Generalized (Converted to birth year)  
- **Justification:** The exact date of birth can be used to identify individuals when combined with other fields. Using only the year reduces this risk.

---

#### 4. Zip Code
- **Type:** Indirect PII  
- **Action:** Partially Masked  
- **Justification:** Full zip codes can reveal precise locations. Masking part of the zip code preserves regional information while protecting privacy.

---

#### 5. Job Title
- **Type:** Indirect PII  
- **Action:** Kept as is  
- **Justification:** Job title alone does not uniquely identify an individual and is useful for analysis.

---

#### 6. Diagnosis Notes
- **Type:** Sensitive Personal Data  
- **Action:** Pseudonymized  
- **Justification:** Medical information is highly sensitive. Pseudonymization ensures privacy while allowing analytical use.

---

### Conclusion
By applying appropriate techniques such as dropping, masking, generalization, and pseudonymization, the dataset is transformed into a privacy-preserving format. This ensures compliance with ethical standards while maintaining its usefulness for research and analysis.

---

## Task 2 — Audit the API Script for Ethical Compliance

### Violation 1: API Key Exposure
- **Problem:** The API key is hardcoded in the script (`free_tier_key_abc123`). This creates a security risk because it can be exposed and misused if the code is shared publicly.
- **Solution:** Store the API key securely using environment variables.

```python
import os
API_KEY = os.getenv("API_KEY")
