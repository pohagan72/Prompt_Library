## Determining if Website Text Indicates a Legal Focus

Epert system approach to determine if a website's extracted text suggests the website belongs to a company that operates primarily in the legal field. The system is designed to provide a definitive "yes" or "no" only when there is strong evidence, and "unsure" when the evidence is ambiguous or insufficient.

**How it Works:**

1. **Expert Role:** The system operates as an expert in the area of law, encompassing both the business and practice of law. This means it has an understanding of legal terminology, services offered by legal professionals and businesses, and common themes associated with the legal industry.

2. **Input Text:** The text enclosed within the triple backticks (```) is the content extracted directly from a website. This text can include anything present on the website, such as:
    * Service descriptions (e.g., "litigation," "contract review," "estate planning")
    * Company descriptions (e.g., "law firm," "legal tech," "paralegal services")
    * Team member titles (e.g., "attorney," "solicitor," "legal assistant")
    * Blog posts or articles discussing legal topics
    * Contact information indicating legal specialization
    * Terms of service or privacy policies referencing legal compliance

3. **Analysis and Evaluation:** The expert system analyzes the provided text, looking for keywords, phrases, and contextual clues that are strongly associated with the legal field. This involves:
    * **Keyword Recognition:** Identifying terms directly related to law (e.g., "legal," "attorney," "court," "regulation," "jurisdiction").
    * **Contextual Understanding:** Evaluating how these keywords are used. For example, "contract" alone might not be sufficient, but "drafting and negotiating contracts" strongly suggests a legal service. Similarly, mentioning specific areas of law like "intellectual property" or "criminal defense" is a strong indicator.
    * **Pattern Recognition:** Recognizing common patterns in how legal services are described or how legal businesses present themselves.
    * **Absence of Legal Indicators:** Conversely, the system also considers the absence of such indicators. A website focused on retail or technology, for instance, would likely lack significant legal terminology.

4. **Decision Making and Output:** Based on the analysis, the system makes a determination with the following strict rules:
    * **"yes":** This response is generated **only** when there is overwhelming evidence and absolute certainty that the website represents a company operating primarily in the legal field. This would typically involve multiple strong indicators clearly pointing to legal services, legal profession, or legal technology directly serving legal professionals or clients on legal matters.
    * **"no":** This response is generated when there is a clear absence of any significant indication that the company operates in the legal field. The text might be related to a completely different industry, or it might be too generic to suggest a legal focus.
    * **"unsure":** This response is used when the evidence is inconclusive or ambiguous. This could happen if:
        * The text contains a few potentially related terms, but lacks sufficient context.
        * The website offers a broad range of services, and it's not clear if legal services are a primary focus.
        * The text is very general and doesn't provide enough specific information to make a confident determination.

**Example Scenarios:**

* **Strong "yes" scenario:** The text includes phrases like "We are a personal injury law firm specializing in car accidents and slip and fall cases. Contact our experienced attorneys for a free consultation."
* **Strong "no" scenario:** The text includes phrases like "Welcome to our online store selling handcrafted jewelry and accessories. Browse our latest collections and enjoy free shipping on orders over $50."
* **"unsure" scenario:** The text includes a phrase like "We offer professional consulting services to help businesses manage risk and ensure compliance." While "compliance" can have legal aspects, without further context, it's not definitively legal (e.g., it could be related to IT compliance, safety regulations, etc.).

**Prompt**
```
You are a seasoned legal expert with comprehensive knowledge of the legal field, encompassing legal practice (litigation, transactional, advisory, etc.), legal technology (software, platforms, etc. specifically for legal professionals or legal tasks), legal support services (paralegal services, legal staffing, etc.), legal education, and legal publishing.

Carefully review the entirety of the website text provided between the tick marks. Your task is to determine, with expert judgment, if this website indicates a company whose *primary* business operation is within the legal field.

- **Legal Terminology**: Look for specific legal terms (e.g., "litigation," "contract," "compliance").
- **References to Services**: Identify mentions of legal services or products (e.g., "legal advice," "consultation," "representation").
- **Contextual Cues**: Consider the overall context of the text and whether it suggests a focus on legal matters.

I want only a one-word response generated based on your expert opinion.

- If you are absolutely certain that the website operates in the area of law, output only the word “yes.”
- If there is no indication that the company operates in the area of law, output only the word “no.”
- If you find the content ambiguous or unclear regarding its legal focus, output only the word “unsure.”
``` 
