# 💳 Financial & Transactional Data Generator

> **Disclaimer:** This dataset contains 100% synthetic dummy data. It mirrors real-world business patterns and data quality anomalies for analytical testing, but contains no actual, confidential, or proprietary information from any real organization or individual.

This directory houses the programmatic generation logic for synthetic, enterprise-grade financial datasets. It is specifically engineered to simulate high-volume transaction logs, fraud indicators, and ledger records riddled with real-world operational noise.

---

## 🎯 Target Use Cases
* **Fraud & Anomaly Detection:** Benchmarking statistical models and classification algorithms against imbalanced, suspicious transaction behavior.
* **Reconciliation ETL:** Stress-testing Pandas, SQL, and data pipeline logic against duplicate entries, currency rounding errors, and out-of-order ledger posts.
* **Financial Reporting:** Practicing complex window functions, aggregations, and rolling metrics on dirty transactional data streams.

---

## ⚡ Injected Operational Noise & Anomalies
To reflect real-world banking and accounting pipeline failures, the generation logic deliberately introduces:

* **Imbalanced Fraud Labels:** Extremely rare positive occurrences (~1–2% of records) mimicking realistic fraud distribution.
* **Negative & Zero Ledger Amounts:** Reversal errors, system glitches, and edge-case operational adjustments.
* **Currency Formatting Inconsistencies:** Mixed string representation (e.g., `$1,250.00`, `1250`, `1250.0`) requiring regex and string-parsing transformations.
* **Duplicate Transaction Keys:** Simulated gateway timeouts leading to double-posted transactions.
* **Timestamp Skew:** Out-of-sequence booking dates vs. actual settlement dates across international time zones.

---

## 🗂️ Data Schema & Dictionary

### `raw_financial_transactions.csv`

| Column Name | Data Type | Constraint / Format | Description & Anomaly Profile |
| :--- | :--- | :--- | :--- |
| `transaction_id` | String | Unique Identifier | Formatted as `TXN_XXXXXXXX` (contains rare duplicates) |
| `account_id` | String | Categorical | Unique customer/account string |
| `timestamp` | Datetime | `YYYY-MM-DD HH:MM:SS` | UTC timestamp (contains out-of-order logs) |
| `merchant_category` | String | Categorical | Industry code (Retail, Travel, Dining, Online, Wire) |
| `amount` | Variant / Float | Mixed Strings & Floats | Transaction value (contains nulls, negative signs, currency symbols) |
| `currency` | String | ISO Code | Primary currency code (`USD`, `EUR`, `GBP`) |
| `is_flagged_fraud` | Integer | Binary (`0` or `1`) | Highly imbalanced target variable |
| `status` | String | Categorical | `SETTLED`, `PENDING`, `FAILED`, or `REVERSED` |

---

## 🚀 How to Run

Ensure your shared virtual environment (`env`) is selected in VS Code, then run the generator script directly:

```bash
python generator.py