## The Challenge: Creating a PowerPoint from any Document

The goal of this prompt is to transform a potentially long document into a well-organized, multi-slide presentation outline. Beyond simple bullet points, the presentation must contain titles, key messages, speaker notes, and even design suggestions. This prompt is designed with precise instruction in mind to create the complex format, in a tone and for an audiance defined by a user, in a specific format that can be transformed into the PowerPoint outline.

## The Prompt
```
You are an expert presentation designer AND coach creating a **robust and detailed first draft** PowerPoint outline (~10-15 slides) with speaker notes and suggestions. Structure information logically for the audience/tone. Ensure bullet points are informative (~10-15 words/short sentences).

**User-Provided Context:**
{context_str if context_lines else "**User Context:** None provided."}

**CRITICAL INSTRUCTIONS:**
1. Generate the entire response following the structure below for **EVERY** slide.
2. **ALL fields listed (Slide Title, Content Type, Key Message, Bullets (at least one), Visual Suggestion, Design Note, Notes, Elaboration, Enhancement Suggestion, Best Practice Tip) ARE REQUIRED for each slide block.** Do not omit fields. Provide meaningful content or state 'None' or 'N/A' where appropriate but the field label MUST be present.
3. Start each slide block *exactly* with `---` on its own line.
4. Ensure bullets start with '- ' and contain substantial information, not just keywords.
5. Elaboration MUST expand significantly on the bullets/key message for the speaker.
6. Enhancement Suggestion and Best Practice Tip MUST be actionable and relevant.

**Required Slide Block Format (Example Included):**

---
Slide Title: [Concise Title in Title Case]
Content Type: [Text Only / Text and Image / Text and Chart / etc.]
Key Message: [**Single sentence essence** tailored for Audience/Tone.]
- [Bullet 1: **Informative point** (~10-15 words/short sentence) directly from or synthesized from the source text.]
- [Bullet 2: (Optional) ditto. Use 3-5 relevant bullets per slide.]
- [...]
Visual Suggestion: [Specific & actionable suggestion (e.g., 'Bar chart comparing Q1 vs Q2 sales', 'Icon representing collaboration') or "Text Focus".]
Design Note: [Optional: Suggest specific emphasis, layout idea, or callout.]
Notes: [Optional: Brief background context, source reference, or data point origin.]
**Elaboration:** [REQUIRED: Expand significantly on the slide's points (2-4 detailed sentences). Provide context, nuance, or talking points for the speaker.]
**Enhancement Suggestion:** [REQUIRED: Offer 1-2 concrete, actionable ideas for the user to improve this specific slide (e.g., 'Add a customer quote here', 'Break this into two slides if time permits').]
**Best Practice Tip:** [REQUIRED: Provide one relevant presentation best practice tip for this type of slide content (e.g., 'Use high-contrast colors for accessibility', 'Limit text to 6 lines per slide').]
---

**Example of ONE complete slide block:**
---
Slide Title: Understanding the Core Problem
Content Type: Text Only
Key Message: Current manual processes lead to significant delays and potential errors in reporting, impacting timely decisions.
- Manual data entry is time-consuming, taking approximately 4 hours per week per analyst involved in the process.
- Lack of real-time validation mechanisms increases the risk of inaccurate financial statements being circulated.
- Reporting delays directly impact the ability of executive leadership to make informed, timely strategic decisions.
Visual Suggestion: Icon representing 'Time Wasted' or 'Error Symbol'. Consider a simple process flow showing the manual steps.
Design Note: Use bold text or a distinct color for the time/delay figures mentioned in the elaboration.
Notes: Data based on internal Q3 process review document and interviews with the finance team.
**Elaboration:** The 4-hour figure represents an average across five analysts; peak times near month-end are higher. Errors identified later require significant rework, sometimes delaying the final month-end close by up to two business days. Leadership relies on these reports for the Wednesday morning strategy meeting, requiring accuracy by EOD Tuesday.
**Enhancement Suggestion:** Quantify the potential financial cost of errors (e.g., average cost per correction, impact of delayed decisions) if possible. Consider adding a brief, anonymous quote from an analyst about the manual process friction.
**Best Practice Tip:** When presenting a problem slide, clearly articulate the 'so what?' – the direct impact on key business objectives or stakeholders (like leadership decision-making).
---

**(Continue generating ALL subsequent slide blocks using the EXACT format above, including ALL required fields)**

**Presentation Flow Guidance (Adapt as needed based on content):**
1. Title Slide, 2. Agenda/Overview, 3. Introduction/Problem Statement, 4. Section 1 (1-3 slides), 5. Section 2 (1-3 slides), 6. Section 3 (1-3 slides) [Adjust section count based on text length/complexity], 7. Key Findings/Analysis (if applicable), 8. Recommendations/Solutions, 9. Next Steps/Call to Action, 10. Conclusion/Summary, 11. Q&A/Contact Information

**Content & Style Guidelines:**
* Structure Comprehensively: Ensure a logical flow from start to finish.
* Informative Bullets: ~10-15 words per bullet, focus on clarity and impact.
* Prioritize Key Info: Extract the most important messages from the source text.
* Tailor Tone/Audience: Reflect the specified audience and tone in language and focus.
* Elaborate Meaningfully: Notes should add real value for the speaker.
* Actionable Suggestions: Enhancements and Tips should be practical.
* Data Storytelling: If data is present, weave it into a narrative.
* Handle Missing Content Gracefully: If source text is sparse for a section, indicate this clearly (e.g., in Notes) but still attempt to generate a placeholder slide with suggestions.

**Source Document Text:**
\"\"\"
{truncated_text}
\"\"\"

Generate the **complete** presentation outline now, following ALL instructions meticulously for **EVERY** slide. Ensure all required fields (Slide Title, Content Type, Key Message, Bullets, Visual Suggestion, Design Note, Notes, Elaboration, Enhancement Suggestion, Best Practice Tip) are present in each block starting with `---`.
"""
```

## Dissecting the Prompt

1.  **Input Parameters:**
    *   `document_text`: The raw text extracted from the user's file.
    *   `template_name`, `audience`, `tone`: User-selected options that provide crucial context for tailoring the presentation's style and content. These are done through the app that was created that uses the prompt.

3.  **Role Setting and Task Definition:**
    ```prompt
    You are an expert presentation designer AND coach creating a **robust and detailed first draft** PowerPoint outline (~10-15 slides) with speaker notes and suggestions...
    ```
    *   Sets the persona and the primary goal for the LLM. Framing it as an "expert designer AND coach" encourages output that includes not just content but also actionable advice (notes, suggestions, tips). Specifying the desired output length (`~10-15 slides`) provides a target scope.

4.  **CRITICAL INSTRUCTIONS - The Core Constraint System:**
        *   **Instruction 1 & 3 (`---` Separator):** `Start each slide block *exactly* with --- on its own line.` This defines a clear, unambiguous delimiter between slide data blocks, which is essential for the `parse_llm_output` function's `re.split(r'\n\s*---\s*\n', llm_text.strip())` logic. Without this reliable separator, parsing would become extremely fragile.
    *   **Instruction 2 (Mandatory Fields):** `**ALL fields listed (...) ARE REQUIRED for each slide block.** Do not omit fields. Provide meaningful content or state 'None' or 'N/A' where appropriate but the field label MUST be present.` This combats the tendency of LLMs to omit information or vary their output structure. By demanding *every* listed field (`Slide Title`, `Content Type`, `Key Message`, `Bullets`, `Visual Suggestion`, `Design Note`, `Notes`, `Elaboration`, `Enhancement Suggestion`, `Best Practice Tip`), the prompt forces the LLM to generate a consistent data structure for *every* slide. The allowance for "None" or "N/A" provides an escape hatch for the LLM when content isn't applicable, but crucially *preserves the field label*, maintaining the parseable structure.
    *   **Instructions 4, 5, 6 (Content Quality):** These instructions guide the *quality* and *depth* of the content within the structure (informative bullets, significant elaboration, actionable suggestions). They push the LLM beyond superficial output.

5.  **Required Slide Block Format & Example:**
    ```prompt
    **Required Slide Block Format (Example Included):**

    ---
    Slide Title: [Concise Title in Title Case]
    Content Type: [Text Only / Text and Image / etc.]
    Key Message: [**Single sentence essence** tailored for Audience/Tone.]
    - [Bullet 1: **Informative point** ...]
    ...
    **Elaboration:** [REQUIRED: Expand significantly...]
    **Enhancement Suggestion:** [REQUIRED: Offer 1-2 concrete...]
    **Best Practice Tip:** [REQUIRED: Provide one relevant...]
    ---

    **Example of ONE complete slide block:**
    ---
    Slide Title: Understanding the Core Problem
    ...
    ---
    ```
    *   **Why:** This provides an explicit template (few-shot learning example) for the LLM. It demonstrates *exactly* how each slide's data should be formatted, including the field names, colons, and expected content style. The concrete example is far more effective than abstract descriptions alone in guiding the LLM's output format. The parser (`parse_llm_output`) directly relies on finding these `Field Name:` prefixes.

6.  **Presentation Flow Guidance:**
    ```prompt
    **Presentation Flow Guidance (Adapt as needed based on content):**
    1. Title Slide, 2. Agenda/Overview, ...
    ```
    *   **Why:** Suggests a logical narrative structure for the presentation, helping the LLM organize the extracted information coherently rather than just listing facts sequentially.

7.  **Content & Style Guidelines:**
    *   **Why:** Reinforces expectations about structure, bullet detail, prioritization, tailoring, elaboration value, and handling sparse data. These act as supplementary quality control instructions.

8.  **Source Document Inclusion:**
    ```prompt
    **Source Document Text:**
    \"\"\"
    {truncated_text}
    \"\"\"
    ```
    *   **Why:** Clearly delineates the user-provided source material that the LLM must base its output on. The triple quotes help manage multi-line text input.

## The Payoff: Enabling Downstream Processing

The meticulous structure enforced by `build_llm_prompt` is not just for the LLM; it's **crucial** for the application's subsequent steps:

1.  **Reliable Parsing (`parse_llm_output`):** This function heavily depends on the predictable format. It splits by `---`, then iterates through lines looking for known prefixes (`Slide Title:`, `Key Message:`, etc.). If the LLM deviated significantly from this format (e.g., omitting fields, changing prefixes, not using `---`), the parser would fail or produce incomplete/incorrect data, breaking the entire workflow. The requirement for *all* fields, even if marked "N/A", ensures the parser can always expect and find each key.
2.  **Structured Data for Generation (`create_presentation`):** The parser produces a list of dictionaries (`slides_data`), where each dictionary represents a slide and contains keys corresponding to the fields mandated in the prompt. The `create_presentation` function then uses this structured data to populate the PowerPoint template, placing the `title`, `key_message`, `bullets`, and importantly, the structured `notes`, `elaboration`, `enhancement_suggestion`, and `best_practice_tip` into the appropriate parts of the slide and notes page (`add_formatted_notes`). Without the prompt enforcing the generation of these specific fields, the final PPTX would be far less valuable.
3.  **Consistency:** While LLM output can still vary, the strict prompt significantly increases the consistency of the output format across different runs and inputs, making the application more robust.

## Conclusion

The `build_llm_prompt` function is far more than just a simple request to the LLM. It is a carefully engineered set of constraints, examples, and context designed to guide the LLM towards generating **structured, detailed, and parsable** output. Its explicit instructions regarding delimiters (`---`), mandatory fields, specific formatting, and content quality are the foundation upon which the subsequent parsing (`parse_llm_output`) and presentation generation (`create_presentation`) steps depend. Without this level of detail and constraint in the prompt, the application would likely produce inconsistent, difficult-to-parse results, failing to reliably deliver the desired rich PowerPoint outline. It exemplifies the critical role of meticulous prompt engineering in leveraging LLMs for complex, structured tasks.
