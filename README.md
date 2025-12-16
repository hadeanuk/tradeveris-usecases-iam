
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
User authenticates to a **Port Community System (PCS)** via Okta, while the OP ensures identity and role verification using vLEI credentials.

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
  

