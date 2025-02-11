# 📝 Prompt for Generating JIRA / DevOps Items for a New Feature

This prompt is designed to help Product Managers generate a comprehensive set of **Epics**, **User Stories**, and **Acceptance Criteria** for a new feature. 

The example provided focuses on a **data integration technology** and a feature for **data cleansing of address details**. The goal is to describe the feature's purpose, its target users, and the expectations for its implementation in a manner that is secure, scalable, and developer-friendly.

---

## 🌟 Example Prompt for Feature Definition

### Scenario:
Imagine you are the Product Manager of a **data integration tool**. You are responsible for defining the most critical capabilities for a **new feature** that will validate address details stored in a database. 

### Feature Overview:
- **Primary Goal**: Identify whether an address in a database is valid.  
- **Scope**: The feature must support addresses from **any country**.  
- **Key Concerns**: The implementation must be **secure** and **scalable**.  

---

## 🔧 Your Role:
As the Product Manager for this feature, you are tasked with the following:
1. **Define requirements** that provide clarity for developers.  
2. Generate structured **Epics**, **User Stories**, and **Acceptance Criteria**.  
3. Use detailed examples and analogies to guide the development team on **expected workflows** and **user experiences**.  
4. Avoid specifying technologies—focus solely on **capabilities**, **user expectations**, and **requirements**.  

---

## Example Output Format:

The output should include the following:

### 1️⃣ **Epics**
High-level descriptions of the feature's primary capabilities. These should outline broad functionality areas.

### 2️⃣ **User Stories**
Detailed user-centric requirements that describe specific tasks or goals users should accomplish with the feature.

### 3️⃣ **Acceptance Criteria**
Clear, testable conditions that define when a feature or story is complete.

---

## ✍️ Example: Generated Requirements for Address Validation Feature

### Epic 1: Address Validation Service
As a user, I want the system to validate the accuracy of an address so that I can ensure my data is reliable and useful.

#### User Stories:
- **Story 1.1**: As a user, I want the system to detect whether an address exists in the real world so that I can remove invalid entries from the database.
  - **Acceptance Criteria**:
    - The system must cross-check the address with a reliable global address database.
    - If an invalid address is detected, the system should flag it with a clear error code and description.
    - The feature must support addresses in all countries and regions.

- **Story 1.2**: As a user, I want the system to suggest corrections for invalid addresses so that I can update my data with valid information.
  - **Acceptance Criteria**:
    - The system should provide suggested corrections for common issues (e.g., misspellings, missing postal codes).
    - When corrections are applied, the system should validate the corrected address before saving.

---

### Epic 2: Scalability and Performance
As a user, I want the address validation feature to handle large-scale datasets efficiently so that I can validate addresses in bulk.

#### User Stories:
- **Story 2.1**: As a user, I want the system to validate thousands of addresses simultaneously without performance degradation.
  - **Acceptance Criteria**:
    - The system must process at least 10,000 addresses per minute.
    - Validation operations must not exceed 2 seconds per address on average.

- **Story 2.2**: As a user, I want the system to provide real-time validation for individual addresses during data entry.
  - **Acceptance Criteria**:
    - The system must validate an address within 1 second of submission.
    - Errors or warnings must appear immediately in the user interface.

---

### Epic 3: Security and Privacy
As a user, I want the address validation feature to handle data securely to ensure compliance with privacy regulations.

#### User Stories:
- **Story 3.1**: As a user, I want all address data to be encrypted during validation to prevent unauthorized access.
  - **Acceptance Criteria**:
    - Address data must be encrypted both in transit and at rest.
    - The system must comply with GDPR, CCPA, and other relevant privacy regulations.

- **Story 3.2**: As a user, I want access to the address validation feature to be restricted to authorized users only.
  - **Acceptance Criteria**:
    - The system must implement role-based access controls (RBAC) for the feature.
    - Unauthorized attempts to access the feature should trigger an alert and be logged.

---

### ⚠️ Notes:
- **Be Verbose**: Provide detailed descriptions for developers to fully understand the feature's requirements and user expectations.  
- **Use Analogies**: Compare functionality to similar well-known products to help clarify workflows or user experiences.  
- **Focus on Outcomes**: Define the "what" and "why," but leave the "how" to the developers.  

---

## 📂 How to Use This Prompt
1. Copy and paste this prompt into your JIRA or Azure DevOps platform to kickstart your requirements gathering process.
2. Customize the **Epics**, **User Stories**, and **Acceptance Criteria** to align with your specific feature needs.
3. Share with your development team to begin the implementation process.

---
