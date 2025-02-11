# Prompt for Generating JIRA / DevOps Items from a GitHub repo

This prompt is designed to help Product Managers generate a comprehensive set of **Epics**, **User Stories**, and **Acceptance Criteria** for a new feature based on reading the files from a GitHub repository.

Tested using https://lmarena.ai/ 

```
### Scenario:
Imagine you are the Product Manager for the product in this github repo. You are responsible for defining the most critical capabilities for it that will be used by developers, QA and documentation to understand what should be built. 

### Feature Overview:
- **Primary Goal**: Identify whether an address in a database is valid.  
- **Scope**: The feature must support addresses from **any country**.  
- **Key Concerns**: The implementation must be **secure** and **scalable**.  

---

## Your Role:
As the Product Manager for this feature, you are tasked with the following:
1. **Define requirements** that provide clarity for developers.  
2. Generate structured **Epics**, **User Stories**, and **Acceptance Criteria**.  
3. Use detailed examples and analogies to guide the development team on **expected workflows** and **user experiences**.  
4. Avoid specifying technologies—focus solely on **capabilities**, **user expectations**, and **requirements**.  

---

## Example Output Format:

The output should include the following:

### **Epics**
High-level descriptions of the feature's primary capabilities. These should outline broad functionality areas.

### **User Stories**
Detailed user-centric requirements that describe specific tasks or goals users should accomplish with the feature.

### **Acceptance Criteria**
Clear, testable conditions that define when a feature or story is complete.

---

### Notes:
- **Be Verbose**: Provide detailed descriptions for developers to fully understand the feature's requirements and user expectations.  
- **Use Analogies**: Compare functionality to similar well-known products to help clarify workflows or user experiences.  
- **Focus on Outcomes**: Define the "what" and "why," but leave the "how" to the developers.
```
