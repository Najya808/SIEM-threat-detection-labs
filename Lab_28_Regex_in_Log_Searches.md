# Lab 28: Regular Expressions in Log Searches

## Objectives
- Understand the basics of Regular Expressions (Regex) and how they are used in log searches.
- Learn to construct regex patterns for identifying specific components in log files.
- Extract and manipulate data from log files using regex.

## Prerequisites
- Basic understanding of file systems and command-line interfaces.
- Familiarity with log files and their general structure.
- A text editor or development environment that supports regex, such as Visual Studio Code, Sublime Text, or `grep` on a Unix-based system.
- Access to sample log files for practice.

---

## Lab Tasks

### Task 1: Constructing Basic Regex Patterns

**Understanding Basic Regex Syntax**
- `.` : Matches any single character except newline.
- `*` : Matches 0 or more of the preceding element.
- `+` : Matches 1 or more of the preceding element.
- `?` : Matches 0 or 1 of the preceding element.
- `[]` : Matches any one of the enclosed characters.
- `^` : Asserts the start of a line.
- `$` : Asserts the end of a line.

**Writing a Simple Regex to Identify IP Addresses**
1. Open your text editor or CLI that supports regex.
2. Use the following pattern to match IPv4 addresses:
```regex
\b(?:\d{1,3}\.){3}\d{1,3}\b
Test the pattern on a sample log file containing IP addresses.

Task 2: Extracting Specific Information from Log Files
Identifying User IDs with Specific Formats

Example: user-123 or ID-456

Regex pattern:

\b(user|ID)-\d+\b
Apply this regex to your log file and highlight all occurrences.

Capturing Error Codes in Log Messages

Example format: [error code: XYZ]

Regex pattern:

\[error code:\s*[A-Z]+\]
Use a tool or script to extract and list unique error codes from the log file.

Task 3: Applying Regex Learnings
Creating a Custom Extraction Script (Python)

import re

log_file_path = 'sample.log'  # Replace with actual log file path

with open(log_file_path, 'r') as file:
    logs = file.readlines()

error_code_pattern = re.compile(r'\[error code:\s*[A-Z]+\]')

for line in logs:
    if error_code_pattern.search(line):
        print(line.strip())
Ensure the script outputs only the lines with matched patterns.

Highlighting Key Matches in Text Editor

Use Visual Studio Code or Sublime Text to highlight matches:

Open search/replace function.

Enter your regex pattern.

Enable regex search to see real-time highlights.

Conclusion
You gained hands-on experience using Regex to search, extract, and manipulate data from log files.

These skills are essential for troubleshooting, data validation, and log parsing.

Practice further with more complex regex patterns and automation scripts.
