# Instruction Dataset Builder for an Intelligent Agriculture Advisory Chatbot Using Generative AI

**Academic Year:** 2026–27  
**Course:** Generative AI and AI Platform Engineering  
**Program:** B.Tech in Computer Science & Engineering  
**Institution:** Koneru Lakshmaiah Education Foundation (KL University), Hyderabad  

### Team Members
* **P. Pranaw Reddy** (`2520030136`)
* **S. Sarveswara Reddy** (`2520030049`)
* **P. Laxman Reddy** (`2520030097`)

**Project Guide:** Dr. V. Anu Ragavi, Assistant Professor, Department of CSE

---

## Overview
Farmers often struggle to access timely, reliable, and easy-to-understand agricultural advice because existing resources are scattered or written in overly technical language. This project presents an **Instruction Dataset Builder** designed to systematically construct, clean, validate, and export high-quality instruction datasets for training or fine-tuning an Intelligent Agriculture Advisory Chatbot using Generative AI.

> **Disclaimer:** The resulting chatbot is intended strictly as an accessible preliminary information-support tool. It does not replace agricultural officers, soil/laboratory testing, or location-specific expert advice.

---

## Key Features
* **Structured Schema Organization:** Converts raw agricultural Q&A pairs into standardized `instruction`, `context`, and `response` fields.
* **Domain Categorization:** Organizes data into core agricultural topics:
  * Crop Management & Selection
  * Soil Preparation & Health
  * Nutrient & Fertilizer Management
  * Irrigation Practices
  * Pest & Disease Control
  * Weather Risks & General Farming Guidance
* **Data Cleaning & Quality Assurance:** Automated handling of missing fields, duplicate removal, text normalization, and consistency checks.
* **Generative AI Draft Assistance:** Uses LLMs/Generative AI to synthesize draft instruction-response examples, paired with human-in-the-loop verification against trusted agricultural references.
* **Multi-Format Export:** Exports validated datasets into standard machine learning formats (`JSON`, `CSV`) or local storage (`SQLite`) ready for model fine-tuning and evaluation.

---

## Software Requirements & Tech Stack
* **Operating System:** Windows 10/11 or Linux
* **Programming Language:** Python 3.x
* **Development Environment:** Visual Studio Code / Jupyter Notebook
* **Frameworks & Libraries:** Streamlit or Flask, Pandas, NumPy
* **Generative AI / NLP:** Hugging Face Transformers or LLM APIs
* **Dataset & Storage:** JSON, CSV, SQLite
* **Version Control & Tools:** Git, Web Browser

---

## Suggested Repository Structure
```text
agriculture-instruction-dataset-builder/
├── data/
│   ├── raw/                  # Unprocessed agricultural Q&A sources
│   ├── processed/            # Cleaned and categorized datasets
│   └── exports/              # Final JSON / CSV instruction datasets
├── src/
│   ├── app.py                # Streamlit / Flask web interface
│   ├── cleaner.py            # Deduplication, formatting, and validation logic
│   ├── generator.py          # Generative AI draft synthesis module
│   └── exporter.py           # JSON, CSV, and SQLite export utilities
├── notebooks/
│   └── exploration.ipynb     # Data exploration and quality analysis
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

---

## Getting Started

### 1. Clone the Repository
```bash
git clone <your-repository-url>
cd agriculture-instruction-dataset-builder
```

### 2. Set Up a Virtual Environment & Install Dependencies
```bash
python -m venv venv
# On Windows:
venv\Scripts\activate
# On Linux/macOS:
source venv/bin/activate

pip install -r requirements.txt
```

### 3. Configure API Keys (Optional for AI Drafting)
If using an external LLM API for draft generation, set your environment variable:
```bash
export LLM_API_KEY="your_api_key_here"
```

### 4. Run the Application
```bash
streamlit run src/app.py
```

---

## Dataset Schema Example
Each exported record follows a standard instruction-tuning structure:
```json
{
  "category": "Nutrient Management",
  "instruction": "What are the signs of nitrogen deficiency in rice crops and how can it be managed?",
  "context": "Paddy cultivation during the vegetative growth stage.",
  "response": "Nitrogen deficiency in rice typically appears as yellowing (chlorosis) starting at the tips of older, lower leaves, accompanied by stunted growth and reduced tillering. To manage this, apply nitrogen-rich fertilizers such as urea in split doses according to soil test recommendations, and maintain proper water levels to prevent nutrient loss."
}
```