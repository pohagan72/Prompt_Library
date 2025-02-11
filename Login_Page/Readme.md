## SaaS Login Page Generation
--------------------

### Table of Contents
- [Description](#description)
- [Prompt](#prompt)
- [Result Prototype GUI](#result-prototype-gui)
--------------------

### Description
A frequent requirement from stakeholders, both internal and external, is to have a fast prototype of an application or feature to support a feedback and review session.

This does not mean a developed solution is required. It means something that *_looks*_ like it could work, and has elements consistent with the desired final version. 

In this scenario, the requirement is for a dynamic and modern login page for a SaaS application which uses specific approved colours from the customer. The prompt used to generate the `index.html` content is:
--------------------

### Prompt

```prompt
I need an HTML file for a login page for a SaaS application. The design should resemble modern login pages found on platforms like Facebook, Google Mail, Outlook.com, Reddit, etc.

**Specific Requirements:**

* **Corporate Branding:**

    * Use the following corporate colors:
        * Primary 1: R: 35, G: 55, B: 70
        * Primary 2: R: 7, G: 77, B: 131
        * Primary 3: R: 0, G: 111, B: 186
        * Primary 4: R: 0, G: 169, B: 224
    * Implement these colors in a professional and visually appealing way, ensuring good contrast for readability.

* **Layout and Elements:**

    * **Logo:** Include a placeholder for the corporate logo at the top of the page.
    * **Heading:** Display a clear "Login" heading.
    * **Input Fields:**
        * Email field with label "Email"
        * Password field with label "Password"
    * **Buttons:**
        * "Sign In" button
        * "Forgot your password?" link
    * **Language Selector:**
        * Dropdown menu allowing users to switch between English, German, French, Spanish, and Brazilian Portuguese.

* **Functionality:**

    * This is purely a visual mockup. No JavaScript functionality is required.

**Output:**

Generate a complete HTML file, with detailed comments, containing the described login page structure and styling.
```
--------------------
### Result Prototype GUI

Index.html file located here: https://github.com/pohagan72/Prompt_Library/blob/main/Login_Page/index.html 

![image](https://github.com/user-attachments/assets/45b86348-a720-4991-a1c8-c4f0f4daa9cf)
