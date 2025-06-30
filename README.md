# Regex_data_cleaning
# 🧼 Regex-Powered Data Cleaning in Python

Welcome to a practical and powerful showcase of **Regex-based data cleaning** using Python and pandas. This project is a step-by-step guide to cleaning messy real-world fields like names, emails, phone numbers, IPs, HTML-tagged text, card numbers, and inconsistent dates — all using the magic of regular expressions (regex). ✨

---

## 🧠 Project Motivation

Messy data is like a bad haircut — everyone notices, and it ruins your day (or model). This notebook demonstrates how to:

- Use regex to extract valid data from noisy inputs.
- Clean and structure fields like names, emails, and phone numbers.
- Validate formats like IP addresses, dates, and credit card numbers.
- Strip unwanted HTML tags and normalize text.

Whether you're preparing data for analysis or building a data QA pipeline — this is your regex Swiss army knife. 🔧

---

## 🗂️ Dataset Snapshot

The raw dataset includes:
- Names with numbers/symbols and HTML.
- Valid and invalid email addresses.
- Phone numbers in different formats.
- IP addresses, some invalid.
- HTML-tagged comments.
- Inconsistent date formats.
- Card numbers in mixed formats or with junk.

---

## ✅ Cleaning Techniques Used

| Column         | Task                                                | Regex Pattern or Method                              |
|----------------|-----------------------------------------------------|-------------------------------------------------------|
| `Name`         | Remove non-alphabetic and HTML tags                 | `re.sub(r'((\<\/?[a-z]\>)|([^a-zA-Z]))','', x)`       |
| `Email`        | Extract valid email formats                         | `str.extract()` with RFC-like regex pattern           |
| `Phone`        | Extract valid 10-digit numbers with/without country | `r'(?:\+[\d]{1,2}\-)?([\d]{10})'`                     |
| `Comment`      | Strip HTML tags to get plain text                   | `re.sub(r'(<.*?>)', '', x)`                           |
| `Date`         | Normalize to YYYY-MM-DD format                      | `dateutil.parser.parse()` with `try/except`          |
| `IP`           | Validate using IPv4 rules (0-255 range)             | Full regex match with 4 octets                        |
| `CardNumber`   | Extract validly structured card numbers             | `r'((?:\d+[ .-]){3}\d+)'`                             |

---

## 📊 Output Preview

Here's a sample of what the cleaned dataset looks like:

| Cleaned_Name | Valid_emails         | Phone_numbers | Text_b/w_tags | Cleaned_date | Valid_IPs   | Valid_CardNumber      |
|--------------|----------------------|----------------|----------------|---------------|-------------|------------------------|
| John         | john.doe@gmail.com   | 9876543210     | Hello there!   | 2023-01-15    | 192.168.1.1 | 4111 1111 1111 1111    |
| Ayesha       | (invalid)            | (invalid)      | Good job       | 2023-01-15    | (invalid)   | 5500-0000-0000-0004    |
| RahulVerma   | ayesha@domain.co.in | 9999999999     | Clean text     | (invalid)     | 10.0.0.1    | (invalid)              |

---

## 🛠️ How to Run

1. Clone this repo:
   ```bash
   git clone https://github.com/your-username/regex-cleaning.git
   cd regex-cleaning
