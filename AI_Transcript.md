# AI_Transcript.md

> **Note:** This transcript is reconstructed from the currently
> available conversation context. It is not a verbatim export of every
> historical message because earlier chat history is not fully
> accessible.

# CSV Header Comparison Tool -- Improved Prompt

## Original Intent

Create a command-line tool that compares the headers of two CSV files.

## Improved Prompt

Build a command-line application in **Java** (or Python/Node.js) that
compares the header rows of two CSV files without using a heavy CSV
parsing library.

### Requirements

1.  Accept two CSV file paths as command-line arguments.
2.  Read **only the first row** from each CSV.
3.  Split the header row using commas.
4.  Trim whitespace around each header.
5.  Compare both header lists.
6.  Report:
    -   Whether the headers match exactly.
    -   Headers only in the expected file.
    -   Headers only in the actual file.
7.  Handle invalid input gracefully (missing files, empty files, invalid
    headers).
8.  Keep the implementation simple using core language libraries only.

## Sample Files

### expected_orders.csv

``` csv
order_id, customer_id, amount, currency, status, created_at, country
1,C001,100.50,GBP,PAID,2026-05-20,UK
2,C002,40.00,GBP,PENDING,2026-05-20,UK
```

### actual_orders.csv

``` csv
order_id, customer_id, total_amount, currency, status, processed_at, country_code
1,C001,100.50,GBP,PAID,2026-05-20,GB
2,C002,40.00,GBP,PENDING,2026-05-20,GB
```

## Topics We Worked Through

-   Java implementation of CSV header comparison
-   Error handling
    -   Missing argument
    -   File not found
    -   Empty CSV
    -   Invalid header row
-   Basic comparison tests
-   Folder structure for Java project
-   Git and IntelliJ commit/push workflow
-   SQL coding task guidance
-   API interview preparation
-   Improvements to coding prompts for interview-quality submissions

## Final Deliverable Checklist

-   [x] Reads only the first row
-   [x] Trims whitespace
-   [x] Compares headers
-   [x] Prints differences
-   [x] Command-line arguments
-   [x] No heavy CSV library
-   [x] Interview-ready Java implementation

## Suggested Project Structure

    CSVHeaderComparison/
    ├── src/
    │   └── HeaderComparison.java
    ├── test/
    ├── data/
    │   ├── expected_orders.csv
    │   └── actual_orders.csv
    └── README.md
