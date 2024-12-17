# Contributing to PTU Resources

## 📝 Table of Contents
- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Style Guidelines](#style-guidelines)
- [First Time Contributors](#first-time-contributors)
- [Pull Request Process](#pull-request-process)

## Code of Conduct

This project adheres to a [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## How Can I Contribute?

### 📚 Adding Study Materials
1. Ensure materials are your own work or properly credited
2. Place files in appropriate semester/subject folders
3. Use clear, descriptive filenames
4. Include source attribution where applicable

### 📝 Adding Question Papers
1. Scan papers in high quality (300 DPI minimum)
2. Name format: `SUBJECT_CODE-YEAR-SEMESTER.pdf`
3. Ensure complete and legible content
4. Remove any personal information

### ✅ Adding Solutions
1. Solutions must be complete and accurate
2. Include step-by-step explanations
3. Use proper formatting and equations
4. Credit sources if using reference materials

## Style Guidelines

### 📂 File Structure

```bash
 Semester-X/
  ├── Subject-Name/
│ ├── Notes/ 
│ ├── Question-Papers/
│ └── Solutions/
```

### 📄 File Naming
- Use kebab-case for folders
- Include subject code where applicable
- Add year and semester for dated content
- Example: `digital-electronics-2023-sem3.pdf`

### 📋 Content Format
- Use Markdown for text content
- LaTeX for mathematical equations
- Clear headings and sections
- Consistent formatting

## First Time Contributors

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/your-username/PTU.git
   ```
3. Create a branch
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. Make Changes
5. Commit with clear messages:
   ```bash
   git commit -m "Add: brief description of changes"
   ```
6. Push changes:
   ```bash
   git push origin feature/your-feature-name
   ```
7. open a Pull Request