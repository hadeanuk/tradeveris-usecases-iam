
# tradeveris-usecases-iam
Mermaid sequence diagrams for identity and federation use cases (OIDC, vLEI, decentralized identity). Designed for review, collaboration, and co-development.

---

## Repository Purpose
This repository provides visual sequence diagrams for authentication and federation flows that combine **OIDC** and **decentralized identity protocols** such as **vLEI** and **KERI**. These diagrams serve as a shared reference for architecture discussions, interoperability design, and implementation planning.

---

## Diagrams Included

### 1. `oidc-federation-bridge.mmd`
**Focus:**  
An **OIDC-centric view** of the federation bridge flow.  
- Shows Okta acting as the relying party (RP) and routing authentication to an external OpenID Provider (OP) that brokers vLEI verification internally.  
- Emphasizes **standard OIDC interactions** (discovery, authorization, token exchange, UserInfo) between Okta and the OP.  
- Abstracts vLEI details, indicating only where vLEI authentication occurs inside the OP domain.  
- Demonstrates how existing IAM platforms can integrate with vLEI without changing downstream applications.

**Use Case:**  
User authenticates to a **Port Community System (PCS)** or any other App protected via Okta, while the OP ensures identity and role verification using vLEI credentials.

---

### 2. `vlei-ipex-auth-flow.mmd`
**Focus:**  
A **vLEI-centric view** of the same federation scenario.  
- Highlights **KERI-based OOBI bootstrap**, **IPEX credential exchange**, and **cryptographic verification** steps.  
- Shows how the OP requires an **ECR credential presentation** before issuing an ID Token to Okta.  
- Details the interaction between the user’s **vLEI wallet**, holder/verifier agents, and the federation bridge.  
- Reduces OIDC boilerplate to keep the emphasis on decentralized identity flows.

**Use Case:**  
User presents vLEI credentials (OOR/ECR) via IPEX to satisfy OP’s policy before completing OIDC login to Okta and accessing the protected application.

---

## Trade Flow Orchestration — Mermaid Sequence Diagrams

The `Trade Flow Orchestration` folder contains Mermaid-based sequence diagrams and flowcharts that illustrate end-to-end trade processes and information architecture for documentary and electronic trade documents. Files included:

- [Trade Flow Orchestration/eBL + eCMR - 1 - buy ship pay.md](Trade%20Flow%20Orchestration/eBL%20+%20eCMR%20-%201%20-%20buy%20ship%20pay.md): Combined eBL and eCMR sequence for a standard "buy → ship → pay" flow showing document lifecycle, carrier interactions, and handoffs between trading parties.
- [Trade Flow Orchestration/eCMR + eBoE - 1 - buy ship pay.md](Trade%20Flow%20Orchestration/eCMR%20+%20eBoE%20-%201%20-%20buy%20ship%20pay.md): eCMR plus electronic Bill of Exchange variant A for buy/ship/pay, focusing on payment triggers tied to transport milestones.
- [Trade Flow Orchestration/eCMR + eBoE - 2 - buy ship pay.md](Trade%20Flow%20Orchestration/eCMR%20+%20eBoE%20-%202%20-%20buy%20ship%20pay.md): Alternate eCMR + eBoE flow (variant B) showing different sequencing for document transfers and payer instructions.
- [Trade Flow Orchestration/eCMR + eBoE - flowchart.md](Trade%20Flow%20Orchestration/eCMR%20+%20eBoE%20-%20flowchart.md): High-level flowchart summarising roles, message types, and primary decision points across the eCMR/eBoE flows.
- [Trade Flow Orchestration/eCMR + eBoE - Information architecture - flowchart.md](Trade%20Flow%20Orchestration/eCMR%20+%20eBoE%20-%20Information%20architecture%20-%20flowchart.md): Information architecture view showing system components, data stores, and integrations for the eCMR/eBoE solution.
- [Trade Flow Orchestration/eCMR + eInvoice + EURC escrow settlement.md](Trade%20Flow%20Orchestration/eCMR%20+%20eInvoice%20+%20EURC%20escrow%20settlement.md): End-to-end diagram covering eCMR, eInvoice issuance and an EURC escrow settlement flow that ties invoice settlement to document and transport events.

Use these diagrams as a reference for implementation planning, orchestration logic, and integration tests. Open the files in VS Code and use the Markdown/mermaid preview to render sequence diagrams.

---

## Render Mermaid in VS Code (Markdown Preview Enhanced)

To view and edit Mermaid diagrams:

1. Install **VS Code** and open this repository.
2. Install the extension:
   - Search for **“Markdown Preview Enhanced”** by Yiyi Wang in the Extensions panel.
3. Open the `.mmd` or `.md` file containing the Mermaid code block:
   ```markdown
   ```mermaid
   sequenceDiagram
   ...
   
