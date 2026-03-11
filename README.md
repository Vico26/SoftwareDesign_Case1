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
### Usability attributes

- Usability: The system must be easy to learn and require minimal training for customs experts.

- Accessibility: The interface should follow accessibility standards such as WCAG to ensure usability for different users.

- Consistency: Navigation and interaction patterns remain uniform across all screens.

- Efficiency: The number of steps required to process documents and generate the DUA should be minimized.

- Clear feedback: The system must clearly inform the user about processing status, errors, and completion.

- Error tolerance: Users must be able to correct extracted information before generating the final document.

- Perceived performance: The system should provide real-time status updates during document processing.

- Trust and credibility: The interface should clearly show confidence levels for extracted data to support expert validation.
#### Core business 

1. The user accesses the application and authenticates into the system.

2. The user provides the location containing the commercial documentation required for the customs declaration.

3. The system scans the provided location and identifies supported document types such as spreadsheets, text documents, PDFs, and scanned images.

4. The system reads the documents and extracts textual information using document parsing and optical character recognition when necessary.

5. The extracted information is analyzed using semantic interpretation models that identify relevant customs data such as importer information, supplier details, product descriptions, quantities, invoice data, transportation details, and country of origin.

6. The system maps the identified information into the corresponding fields defined by the official DUA template.

7. The system validates the consistency of the extracted information, checking elements such as value totals, currencies, and date coherence.

8. Fields with uncertain or ambiguous data are flagged for later verification.

9.  The processed information is prepared for user review and document generation.
#### Login
1. The user provides authentication credentials to access the application.

2. The system validates the credentials against the authentication service.

3. If the credentials are valid, the system grants access to the application and initializes the user session.

4. If the credentials are invalid, access is denied and the user is requested to attempt authentication again.
- Wireframe proposed:![Login](/Media/Login.png)
#### Process Monitoring
1. After submitting the documentation for processing, the user observes the status of the analysis process.

2. The system reads each document and extracts relevant information.

3. The system updates the processing status as each document is analyzed.

4. If a document cannot be processed, the system records the issue and continues processing the remaining documents.

5. Once all documents have been analyzed, the system prepares the extracted data for validation.
- Wireframe proposed: ![Process Monitoring](/Media/Process%20Monitoring.png)
#### Result retrival
1. The user reviews the extracted data that has been mapped to the DUA structure.

2. The user verifies the detected information and corrects any fields that require manual validation.

3. Once the data is confirmed, the user requests the generation of the final DUA document.

4. The system generates a structured document based on the official DUA template.

5. The final document is made available to the user for download and further submission to customs authorities.
- Wireframe proposed: ![Result retrival](/Media/Result%20retrival.png)
#### Logout
1. The user decides to terminate the session.

2. The system invalidates the active session and removes authentication credentials.

3. The user is redirected to the authentication page.
- Wireframe proposed: ![Logout](/Media/Logout.png)

### User profiles

- Customs expert: Validates extracted information and confirms the final DUA document.

- Administrative operator: Provides the documentation folder and initiates the processing.

- Technical administrator: Maintains system availability and monitors processing performance.

---
### Usability testing with Figma prototype

To validate the proposed user experience, an interactive prototype of the application was created using Figma Make. The prototype simulated the main application flows, allowing early evaluation of navigation, task execution, and user understanding before implementing the frontend.

The prototype includes the following screens:

Login

Document processing monitoring

Result validation and retrieval

Logout

The prototype was shared with participants through a Figma link, allowing them to interact with the interface and simulate the main workflow of the system.

Prototype reference:
https://www.figma.com/make/vSs0bAkQqgcF7eKFAex6eS/DUA-Streamliner-Automation?t=r4zk6ta8m28VLHmm-20&fullscreen=1

### Testing Participants
| Participant | Profile | Experience with Document Processing | Notes |
|-------------|--------|--------------------------------------|------|
| Gilda Castro | Computer engineer | High | Regularly works with commercial documentation |
| Aura Martínez | Business administrator| Medium | Familiar with customs declaration processes |
| Leopoldo Martínez | Electrical engineer and farmer | Low | Experience handling commercial documentation |
| Gastón Molina | General web user | Medium | Familiar with web applications but not with customs workflows |

## Results
| Task | Success Rate | Average Time | Observations |
|-----|--------------|--------------|--------------|
| Login to the system | 100% | 2 minutes | All users understood the authentication process without issues |
| Provide documentation folder | 20% | 45 seconds | User took sometime to locate the documents needed for the test |
| Monitor document processing | 100% | 10 seconds | Some users expected more visual feedback during processing |
| Validate extracted data | 75% | 5 minutes | Some users hesitated when reviewing fields flagged with medium confidence |
| Generate DUA document | 100% | 20 seconds | Users clearly understood the final generation step |
| Logout from the system | 80% | 15 seconds | No usability issues detected, but the least experienced took a little longer to logout the system|

---
### Component Design Strategy

The frontend follows a modular component-based architecture using React.

Reusable UI components are created to ensure consistency across the application.

#### Component reuse

Reusable components include:

- Button
- InputField
- StatusIndicator
- DocumentList
- ValidationField

These components are placed in a shared components directory to allow reuse across pages.

#### Style centralization

Styling is centralized using a global theme configuration.

- Global styles defined in `/styles`
- Shared color palette for confidence indicators
- Consistent typography and spacing

#### Branding

Brand identity elements such as colors, icons, and typography are defined in a centralized theme configuration.

#### Internationalization

Text labels are separated from components to allow future support for multiple languages.

#### Responsiveness

Responsive layouts are implemented using flexible containers and breakpoints to ensure usability across desktop and tablet devices.

---
### Security

Security in the frontend focuses on authentication, authorization, and session management.

#### Authentication

Authentication is handled through a secure login flow that validates user credentials against an authentication service.

Authentication tokens are stored securely and attached to API requests.

#### Authorization

User roles define access permissions:

- Customs Expert
- Administrative Operator
- Technical Administrator

Role validation is performed before allowing access to protected routes.

#### Session Management

Sessions are managed using secure tokens.

Session expiration automatically invalidates access and redirects users to the login screen.

Protected routes ensure that only authenticated users can access application features.

---
### Layered Design

The frontend follows a layered architecture to separate responsibilities and improve maintainability.

#### Presentation Layer

Contains UI components responsible for rendering the interface.

Examples:

- Login page
- Process monitoring page
- Result validation page

#### Application Layer

Handles user interaction logic and state management.

Examples:

- Form validation
- Processing state updates
- UI event handling

#### Service Layer

Responsible for communication with backend services.

Examples:

- Document processing API calls
- Authentication service requests
- DUA generation requests

#### Integration Layer

Handles external service communication such as AI processing and document analysis APIs.

---
### Design Patterns

Several design patterns are applied in the frontend architecture.

#### Observer Pattern

Used to update the UI when document processing status changes.

#### Singleton Pattern

Applied to maintain a single instance of the API client used for backend communication.

#### Factory Pattern

Used to create standardized UI components such as validation fields based on data type.

#### Strategy Pattern

Used to handle different document validation rules depending on document source.

---
### Project Scaffold

The project structure follows a modular organization to improve maintainability and scalability.

/src
 ├── assets
 │
 ├── components
 │    ├── Button
 │    ├── InputField
 │    ├── StatusIndicator
 │    └── DocumentList
 │
 ├── pages
 │    ├── Login
 │    ├── ProcessMonitoring
 │    ├── ResultValidation
 │
 ├── services
 │    ├── authService.ts
 │    ├── documentService.ts
 │    └── duaService.ts
 │
 ├── hooks
 │
 ├── styles
 │    ├── theme.ts
 │    └── global.css
 │
 ├── routes
 │    └── AppRouter.tsx
 │
 ├── utils
 │
 ├── App.tsx
 └── main.tsx

