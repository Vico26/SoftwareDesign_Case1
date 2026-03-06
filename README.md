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
- Web framework: ReactJs v19.2
- Web server: Vite Dev Server v5
- Language: TypeScript v5.9.3
- Routing: React Router v6.x
- Data validation: Zod v4.3.6
  
- Unit testing: 
  - Jest v30.2.0
- Integration testing: 
  - Playwright v1.58.2
  
- Build tool: Vite v5
- Code automation task tool: Husky v9.1.7
-  Listing & Formating: 
   - Prettier version v3.8.1
   - EsLint version v10.0.2

- Cloud and Deployment:
  - Cloud: Azure Cloud Services 
  - Hosting: Azure App Service (PaaS)
  
- Code repositories: Azure DevOps Repos
- CI/CD: Azure DevOps Pipelines

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
### 1.2 UX UI Analysis
#### Core business 
1.  Describe the sequence of actions that the user performs and how the system responds in order to generate the DUA document.

2. The user accesses the application and authenticates into the system.

3. The user provides the location containing the commercial documentation required for the customs declaration.

4. The system scans the provided location and identifies supported document types such as spreadsheets, text documents, PDFs, and scanned images.

5. The system reads the documents and extracts textual information using document parsing and optical character recognition when necessary.

6. The extracted information is analyzed using semantic interpretation models that identify relevant customs data such as importer information, supplier details, product descriptions, quantities, invoice data, transportation details, and country of origin.

7. The system maps the identified information into the corresponding fields defined by the official DUA template.

8. The system validates the consistency of the extracted information, checking elements such as value totals, currencies, and date coherence.

9. Fields with uncertain or ambiguous data are flagged for later verification.

10. The processed information is prepared for user review and document generation.
#### Login
#### Monitoreo del avance
#### Obtencion del resultado
#### Logout
#### Wireframes
