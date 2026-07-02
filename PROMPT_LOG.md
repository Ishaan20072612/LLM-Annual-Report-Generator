# Prompt Log

## Model Used
gpt-4.1-mini

## Objective
Generate a completely fictional annual report based on the structure of a sample annual report.

## Prompt 1
Generate the introduction section of a fictional annual report.

### Inputs
- Company Name
- Industry
- Headquarters
- Year Founded

### Constraints
- Professional annual report style
- Around 250 words
- Completely fictional
- Do not mention Tata Power

---

## Prompt 2
Generate a complete fictional annual report.

### Sections
- Introduction
- Key Highlights
- Financial Summary
- Company Assets
- Breakthrough Projects
- Future Outlook
- References

### Constraints
- 1200–1500 words
- Professional tone
- Fictional data
- Use headings
- No copied content

---

## Libraries Used

- openai
- python-dotenv
- pymupdf
- matplotlib
- reportlab

---

## Workflow

1. Load PDF
2. Extract text
3. Analyze structure
4. Extract company information
5. Create fictional company
6. Connect to OpenAI
7. Generate report
8. Generate charts
9. Export final PDF