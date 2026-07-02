# LLM Annual Report Generator

An AI pipeline that reads a sample financial annual report, extracts its structure and themes, and generates a complete fictional annual report for a different company — with fake data, charts, and a formatted PDF output.

Built as part of an LLM engineering challenge.

---

## What It Does

1. Reads a sample PDF annual report (Tata Power / financial format)
2. Extracts structure — section titles, financial table formats, chart types, tone
3. Creates a fictional company with fake financials
4. Uses GPT-4.1-mini to generate each section of the report
5. Generates 2 charts with matplotlib (revenue growth line chart + asset distribution pie chart)
6. Exports the full report as a formatted PDF using ReportLab

---

## Output

The generated report (`report_output.pdf`) includes:

- **Introduction** — company background and vision
- **Key Highlights** — bullet-point achievements
- **Financial Summary** — tabular data with fake but realistic numbers
- **Company Assets** — manufacturing plants, offices, workforce
- **Breakthrough Projects** — 3 fictional innovations
- **Future Outlook** — 5-year strategic roadmap
- **References** — 10 fictional citations

Plus 2 visualizations:
- Revenue Growth line chart (2020–2023)
- Company Asset Distribution pie chart (Solar, Wind, Grid, Hydrogen)

---

## Sample Output

**Company:** Solara Grid Renewables Limited  
**Industry:** Renewable Energy  
**Headquarters:** Hyderabad  
**Report Year:** 2023  
**Word Count:** 1,200+ words  

---

## Project Structure

```
├── solution.ipynb          # Fully executed Jupyter notebook
├── report_output.pdf       # Generated fictional annual report
├── PROMPT_LOG.md           # All prompts, models, libraries, and architectural decisions
├── requirements.txt        # Python dependencies
├── sample_input_1.pdf      # Sample input annual report (Tata Power - Geojit)
├── sample_input_2.pdf      # Sample input annual report (Tata Power - Anand Rathi)
├── chart1.png              # Revenue Growth chart
└── chart2.png              # Asset Distribution chart
```

---

## Workflow Architecture

```
Sample PDF
    |
    v
PDF Text Extraction (pdfplumber / pymupdf)
    |
    v
Structure Analysis
  - Section titles
  - Financial table format
  - Chart types
  - Company metadata
    |
    v
Fictional Company Creation
    |
    v
GPT-4.1-mini Content Generation
  - Prompt 1: Introduction (~250 words)
  - Prompt 2: Full report (1200-1500 words)
    |
    v
Chart Generation (matplotlib)
  - Revenue Growth Line Chart
  - Asset Distribution Pie Chart
    |
    v
PDF Assembly (ReportLab)
    |
    v
report_output.pdf
```

---

## Setup

```bash
git clone https://github.com/Ishaan20072612/LLM-Annual-Report-Generator.git
cd LLM-Annual-Report-Generator
pip install -r requirements.txt
```

Set your OpenAI API key as an environment variable:
```bash
export OPENAI_API_KEY=your_key_here
```

Then open and run `solution.ipynb` in Jupyter.

---

## Requirements

```
openai
python-dotenv
pymupdf
matplotlib
reportlab
pandas
numpy
pdfplumber
```

---

## Prompt Strategy

All prompts, model choices, temperature settings, architectural decisions, and prompt iterations are documented in `PROMPT_LOG.md`.

**Model used:** `gpt-4.1-mini`  
**Key design decision:** Two-stage prompting — first extract structure, then generate content section by section to maintain consistency and avoid hallucination drift across a long document.

---

## Tech Stack

| Library | Purpose |
|---------|---------|
| `openai` | GPT-4.1-mini for text generation |
| `pdfplumber` | PDF text extraction |
| `pymupdf` | Alternative PDF parsing |
| `matplotlib` | Chart generation |
| `reportlab` | PDF assembly and formatting |
| `python-dotenv` | API key management |

---

## Author

Ishaan Chowdhury · [@Ishaan20072612](https://github.com/Ishaan20072612)
