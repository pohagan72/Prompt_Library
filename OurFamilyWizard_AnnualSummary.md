This is the prompt from the MyFamilyWizard AI Agent for summarizing activities by year. 


```
Synthesize the provided monthly analyses for the entire year {year} involving participants {participants}.

Your goal is to create a single, consolidated YEARLY analysis. Provide this yearly analysis STRICTLY in the following JSON format. Do not include any text before or after the JSON object. Ensure the JSON is valid:
{{
"summary": "Provide a concise overarching summary of the key discussion themes, major decisions, significant events, and overall communication patterns observed throughout the entire year {year}.",
"drug_mentions": [],
"alcohol_mentions": [],
"money_mentions": [],
"conflict_negativity_analysis": "Describe the dominant sentiment and tone across the whole year {year}. Highlight recurring conflicts, significant negative interactions, or overall trends in negativity/positivity observed across the months. Mention if the tone shifted significantly during the year."
}}

Instructions for Yearly Synthesis:
•	Review all the monthly data provided below.
•	For "summary": Create a high-level summary covering the entire year. Do not just list monthly summaries; synthesize the key points and trends.
•	For the lists "drug_mentions", "alcohol_mentions", "money_mentions":
o	Aggregate the most significant or recurring mentions from the *monthly* reports. You do not need to include *every single* mention from the entire year if there are many duplicates or minor instances. Prioritize clarity and significance for the yearly overview.
o	The format MUST remain a JSON list of objects, each with "timestamp", "sender", and "quote". Ensure you include the sender's name associated with each aggregated quote.
o	If NO significant mentions were noted across the year in the monthly reports for a category, return an empty list (e.g., "drug_mentions": []).
•	For "conflict_negativity_analysis": Provide a holistic view of the conflict and tone for the year. Identify major arguments, persistent issues, or overall relationship dynamics evident from the monthly analyses. Note any significant escalations or de-escalations.
```
