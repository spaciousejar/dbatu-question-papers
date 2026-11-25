# Contributing to the Question Papers of DBATU University

Thank you for your interest in contributing to this repository! Please follow these guidelines.

## Repository Structure

```
Branch/
  Nth Semester/
    Subject/
      Subject-W-2023.pdf        # Winter 2023
      Subject-S-2024.pdf        # Summer 2024
      Subject-2025.pdf          # Year only (session unknown)
      Subject-2-Supp.pdf        # Supplementary paper
      Subject-Assignment.pdf    # Assignment
      Subject-Notes.pdf         # Notes
```

## Directory Structure

| Branch | Folder |
|--------|--------|
| Common subjects (1st/2nd year) | `1 year common to all/` |
| Computer Science | `Computer science engineering/` |
| Electronics & Computer | `Electronics and computer engineering/` |
| Electronics & Telecom | `Electronics and Telecommunication engineering/` |
| Mechanical | `Mechanical Engineering/` |
| Civil | `Civil Engineering/` |
| Chemical | `Chemical & Petrochemical Engineering/` |
| AI & Data Science | `Artificial Intelligence & Data Science/` |
| B.Pharm | `Pharmacy - B.Pharm/` |
| M.Pharm | `Pharmacy - M.Pharm/` |
| Electrical | `Electrical Engineering/` |
| Mechatronics | `Mechatronics Engineering/` |
| Biomedical | `Biomedical Engineering/` |
| Syllabus PDFs | `Syllabus/<Branch>/` |

Put full syllabus PDFs in `Syllabus/<Branch>/`. Do not put them in question-paper folders. Add them as normal files. Do not use Git LFS.

## File Naming Convention

```
Subject[-Metadata]-YYYY-MM.pdf
```

**Examples:**
- `Engineering Mathematics-2025-02.pdf`
- `Data Structures-2024-07.pdf`
- `Operating Systems-2-Supp-2025-02.pdf`
- `Digital Electronics.pdf` (date unknown)

**Rules:**
- Subject name: Title Case, spaces not underscores
- Hyphens separate metadata fields
- Use the exact exam date shown in the PDF.
- Use `07` for Summer and `02` for Winter when the PDF has no exact date.
- Put the date at the end of the filename.
- No subject codes or college codes in filenames
- Remove contributor tags like `{Pran Tehare}`

## How to Contribute

Before you start, check [INDEX.md](INDEX.md) for the paper you want to add.

1. **Fork** the repository
2. **Create a branch**: `git checkout -b add-physics-papers`
3. **Place papers** in the correct `Branch/Nth Semester/Subject/` folder
4. **Name files** following the convention above
5. **Commit**: `git commit -m "Add Engineering Physics Winter 2023 papers"`
6. **Push and open a Pull Request**

## What to Include

- Previous year question papers (PYQ)
- Supplementary/re-appear papers
- Model answer papers
- Assignments (if they contain practice questions)

## What NOT to Include

- Textbooks
- Personal notes unrelated to exams
- Duplicate copies of papers already in the repo
- Large files (>20 MB) — link to external hosting instead

## Checking for Duplicates

Before submitting, check [INDEX.md](INDEX.md) to see if the paper already exists. Each subject folder may have multiple papers — look for matching year and session before adding.
