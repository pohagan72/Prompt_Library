---

# Advanced Competitive Analysis Prompt Shell

This document provides a reusable, advanced prompt shell designed to instruct an AI agent to generate a comprehensive competitive analysis report. It is structured to produce a detailed, well-organized, and actionable document suitable for strategic business purposes.

---

## The Prompt

> **Persona:**
> You are a senior competitive intelligence analyst.
>
> **Objective:**
> Your task is to conduct a comprehensive competitive analysis of **[Product/Company Name, e.g., Consilio Aurora]**. If it is a product, analyze it within the context of its parent company, **[Parent Company Name, e.g., Consilio]**. This report is being prepared for **[Your Company Name, e.g., Epiq Global]** and must provide deep, actionable insights for our sales and strategy teams to effectively pitch against them.
>
> **Process:**
> 1.  Use the search tool to find up-to-date and relevant information. Focus your searches on the official website(s), recent press releases, industry news, credible financial and company comparison data sources (like Tracxn, Comparably, Gartner), and community discussions (such as on Reddit).
> 2.  If analyzing a product, investigate the parent company's market position, reputation, and overall strategy to understand how the product fits into its portfolio.
> 3.  Browse the most relevant URLs from your search results to extract specific facts, figures, claims, and market sentiment.
> 4.  Synthesize the gathered information into a structured, in-depth report following the exact format and sections outlined below.
>
> **Required Report Structure and Content:**
>
> **Executive Summary:**
> A concise overview of the subject's market position, key differentiators, financial/organizational backing, primary offerings, and the strategic implications for **[Your Company Name]**.
>
> **1. Introduction and Market Context:**
>     *   1.1. Parent Company Profile (if applicable): Briefly describe the parent company's role as a market leader and its core services.
>     *   1.2. Genesis of the Product/Company: What specific market challenges or customer pain points was it created to solve? What is its stated mission?
>
> **2. Technical Architecture and AI Capabilities:**
>     *   2.1. Core Components & Architecture: Describe the underlying technology (e.g., "DataCore," "private cloud infrastructure").
>     *   2.2. AI-Powered Solutions: List and describe the main AI-driven features (e.g., "Native AI Review," "AI Summarize").
>     *   2.3. Data Security and Infrastructure: Detail the approach to data security, privacy, and infrastructure (e.g., private vs. public cloud).
>     *   2.4. Strategic Technology Partnerships: Detail any key technology partnerships that enhance its capabilities.
>
> **3. Media and Community Perception:**
>     *   3.1. Official Announcements: Summarize the key messages from official launch press releases.
>     *   3.2. Industry News Coverage: How have legal tech publications and analysts covered it? Note the absence of negative mentions if applicable.
>     *   3.3. Social Media & Community Sentiment: What are users on platforms like Reddit or X saying? Capture any confusion, skepticism, or early praise.
>
> **4. Customer and Market Adoption:**
>     *   4.1. Target Clientele & Stated Benefits: Who is the ideal customer? What value proposition is offered to them?
>     *   4.2. Analysis of Testimonials & Case Studies: Summarize available partner or customer testimonials. Note the absence of direct end-client case studies, especially if the product is new.
>
> **5. Competitive Landscape and Strategic Positioning:**
>     *   5.1. Key Competitors: Identify primary competitors. Include any available quantitative comparison data (e.g., from Comparably, G2, Gartner).
>     *   5.2. Unique Selling Propositions (USPs): What are its key differentiators (e.g., platform freedom, unified control, pricing model)?
>     *   5.3. Pricing Model Analysis: Describe their stated pricing. Contrast this with any user-reported feedback on actual costs or complexity.
>     *   5.4. Strategic Pitching Insights for **[Your Company Name]**:
>         *   Leverage **[Your Company Name]'s** strengths against the competitor.
>         *   Exploit the competitor's potential weaknesses or market challenges.
>
> **6. Conclusion and Strategic Outlook:**
>     *   6.1. Overall Assessment: Summarize the core strengths and market opportunities.
>     *   6.2. Potential Challenges and Vulnerabilities: Summarize key challenges, such as market confusion, reliance on partners, or pricing concerns.
>     *   6.3. Broader Strategic Implications: How does this product/company reflect larger trends in the market (e.g., legal automation, AI adoption)? What are the long-term strategic implications for the industry?
>
> **Formatting and Citation Requirements:**
> *   The final output must be a professional, well-structured document.
> *   Use headings, subheadings, bullet points, and tables to organize information clearly.
> *   **Crucially, every piece of information or claim sourced from your research must be followed by a citation, like this.**
> *   Conclude with a numbered "Works Cited" list that corresponds to the citations in the text.

---

## Breakdown and Explanation of the Prompt

This section explains the purpose and importance of each part of the prompt.

### `Persona`
*   **Prompt Text:** `You are a senior competitive intelligence analyst.`
*   **Explanation:** This sets the role and tone for the AI. It instructs the agent to adopt the mindset of an experienced professional, focusing on analytical depth, strategic insight, and a formal, business-appropriate tone rather than a casual summary.

### `Objective`
*   **Prompt Text:** `Your task is to conduct a comprehensive competitive analysis of...`
*   **Explanation:** This is the mission statement. It clearly defines the target (`[Product/Company Name]`), the context (`[Parent Company Name]`), and the end goal: creating **actionable insights** for a specific audience (`[Your Company Name]'s sales and strategy teams`). This focus on actionability ensures the final report is not just informational but useful.

### `Process`
*   **Prompt Text:** `1. Use the search tool... 2. If analyzing a product...`
*   **Explanation:** This section outlines the specific steps the AI agent should follow to gather information.
    *   **Step 1:** Specifies the *types* of sources to prioritize, guiding the agent toward high-quality, relevant data (official sites, financial data, community forums).
    *   **Step 2:** Adds a critical instruction to investigate the parent company, ensuring a product isn't analyzed in a vacuum.
    *   **Step 3 & 4:** Dictates the workflow of browsing sources and then synthesizing the findings into the required structure, preventing the AI from just listing facts without analysis.

### `Required Report Structure and Content`
This is the most critical part of the prompt, as it defines the exact schema for the final output. The detailed structure forces the AI to organize its findings logically and cover all essential angles of a thorough competitive analysis.

*   **`Executive Summary`**: Ensures the report starts with a high-level overview, making it accessible to busy stakeholders.
*   **`1. Introduction and Market Context`**: Frames the analysis by establishing the company's background and the market problem it aims to solve (its "Genesis").
*   **`2. Technical Architecture and AI Capabilities`**: Dives into the *how* of the product. It demands specifics on technology, AI features, security, and partnerships, moving beyond marketing claims to technical substance.
*   **`3. Media and Community Perception`**: Captures the external view. This section seeks to understand both the official narrative (media) and the "ground truth" (community sentiment), which often reveals crucial discrepancies.
*   **`4. Customer and Market Adoption`**: Focuses on the go-to-market aspect. It asks *who* the product is for and what proof exists of its adoption and success (testimonials, case studies).
*   **`5. Competitive Landscape and Strategic Positioning`**: This is the core competitive section.
    *   `5.1. Key Competitors`: Forces a direct comparison, ideally with quantitative data.
    *   `5.2. Unique Selling Propositions (USPs)`: Asks the AI to distill the competitor's core differentiators.
    *   `5.3. Pricing Model Analysis`: A key point of vulnerability for many tech products. It specifically asks to contrast official claims with user reports.
    *   `5.4. Strategic Pitching Insights`: This is the ultimate payoff of the analysis. It explicitly asks the AI to synthesize all previous points into direct, actionable advice for your team.
*   **`6. Conclusion and Strategic Outlook`**: Broadens the view to the future. It summarizes the findings and connects them to larger market trends, adding a layer of strategic foresight.

### `Formatting and Citation Requirements`
*   **Explanation:** These final instructions are crucial for quality control.
    *   **Structure:** Ensures the output is clean and readable (headings, tables).
    *   **Citations:** This is a non-negotiable requirement for any credible research. It forces the AI to back up every claim with a source, ensuring the report is verifiable and trustworthy.
    *   **Works Cited:** Completes the citation process, making it easy to review the source material.

By using this detailed and structured prompt, you guide the AI to act as a methodical analyst, resulting in a report that is comprehensive, credible, and strategically valuable.
