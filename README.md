## Overview

The **Baby Names Utility (`bn`)** is a Bash program that processes historical U.S. baby name data from the [Social Security Administration](https://www.ssa.gov/oact/babynames/limits.html). It allows users to query name rankings based on year and gender while handling edge cases gracefully. The project also integrates a CI pipeline to ensure code quality and robustness.

## Key Features

- **Efficient Data Processing**: Uses pipes, filters, and regular expressions to parse and analyze large datasets dynamically.
- **Error Handling**: Comprehensive validation for input arguments, data formats, and edge cases.
- **Extensible Design**: Dynamically adapts to changes in the dataset, ensuring flexibility without hardcoding assumptions.
- **Help Utility**: Includes a `--help` flag that displays usage and argument details.
- **CI Pipeline**: Automates testing on every push for reliability and maintainability.

---

### Usage
Command Format:
```bash
bn <year> <assigned gender: f|F|m|M|b|B>
```

### Arguments:
- **`<year>`**: A four-digit integer representing the year.
- **`<assigned gender>`**: One of `f`, `F`, `m`, `M`, `b`, or `B`:
  - `f` or `F` for female names.
  - `m` or `M` for male names.
  - `b` or `B` for both male and female names.

### Input:
- A list of whitespace-separated names provided via **standard input**.

### Output:
- The rank of each name for the given year and gender(s).

### Example:
```bash
$ bn 1969 M
sam SCOTT Bob
1969: sam ranked 318 out of 5042 male names.
1969: SCOTT ranked 12 out of 5042 male names.
1969: Bob ranked 380 out of 5042 male names.
lucy
1969: lucy not found among male names.
