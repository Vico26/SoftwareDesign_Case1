# DUA Streamline
## Author
Victoria Molina Martínez
## Overview
DUA Streamliner is an automated system designed to drastically simplify the preparation of the Documento Único Aduanero (DUA). It extracts, interprets, and maps information from multiple document formats into the official DUA template, generating a pre-filled Word file for expert validation.

---

## System Input

- User provides only a **folder path** (local or network).
- The folder may contain:
  - Excel (.xlsx)
  - Word (.docx)
  - PDF files
  - Scanned images (invoices or documents)
- No rigid predefined formats required.
- The system interprets heterogeneous document structures.

---

## Intelligent Processing

### a) Multi-Format Reading
- Reads Word and Excel files.
- Extracts structured and unstructured text from PDFs.
- Uses advanced OCR for scanned images.

### b) Semantic Extraction (AI-Based)
The system identifies:

- Importer/exporter data  
- Supplier information  
- Commercial and tariff description of goods  
- Quantities, weights, FOB/CIF values  
- Incoterms  
- Transport information  
- Invoice number and date  
- Country of origin and shipment  
- Applicable customs regime  

Extraction is contextual, not just keyword matching, allowing interpretation across different document structures.

---

## Mapping to Official DUA Template

- Automatically maps extracted data to official DUA fields.
- Performs basic validation:
  - Value totals
  - Currency consistency
  - Date consistency
- Flags ambiguous or low-confidence fields.

---

## Output Generation

- Generates a pre-filled Word (.docx) DUA document.
- Uses visual confidence coding:
  - Green → High confidence
  - Yellow → Medium confidence
  - Red → Requires review

---

## Core Objective

- Does not replace the customs expert.
- Transforms the expert into a strategic validator.
- Reduces repetitive manual work and minimizes errors.

---

## 1. Frontend Design
### 1.1 Technology Stack

- Application type: Web app
- Web framework: ReactJs version 19.2
- Web server: NodeJs v2 HTTPS 
- Language: TypeScript version 5.9.3
- Routing: React Router version 6.x
- Data validation: Zod 4.3.6
  
- Unit testing: 
  - Jest 30.2.0
- Integration testing: 
  - Playwright
  
- Build tool: Vite version 5
- Code automation: Husky v9.1.7
- Cloud and Deployment:
  - Cloud: Azure Cloud Services
  - Hosting: Azure App Service
  
- Code repositories: Azure DevOps Repos
- CI/CD: Azure DevOps Pipelines
- Listing & Formating: 
  - Prettier version 3.8.1
  - EsLint version 10.0.2

- Environments:
  - Development
  - Stage
  - Production
- Environment deployment tools:
  - Azure DevOps Environments
  - Azure App Service Deployment Slots

- Observability framework:
  - Azure Monitor
  - Azure Application Insights
