# a11y-jam-sessions
Our casual, friendly online jam to learn about accessibility in Design Systems









# Appendix

## Accessible Component Design Decision Tree

### How to Use This Decision Tree:

This decision tree helps you check if your component meets accessibility standards. Follow these steps in order:
	
1.	Start with WCAG A
	•	Make sure everyone can use your component.
	•	Check keyboard access, labels, focus visibility, and alt text for images.
2.	Move to WCAG AA if A is complete
	•	Improve contrast so text is easy to read.
	•	Make sure users can resize text without breaking the layout.
	•	Add captions for videos and check focus order.
3.	Check if AAA is needed
	•	Some projects, like government or inclusive products, may need extra features.
	•	AAA includes sign language for videos, high contrast text, and more customization options.

Your component is ready when all required levels are met.

```mermaid
graph TD;
    A1[Start: Designing a Component] --> B1{Is it a core feature or interactive?};
    B1 -->|Yes| C1{Does it meet WCAG A?};
    B1 -->|No| C2[Not required to meet strict WCAG, but best practices recommended];

    C1 -->|No| D1[Fix Basic Issues];
    D1 --> D1a[Ensure keyboard navigability];
    D1 --> D1b[Provide meaningful alt text for images];
    D1 --> D1c[Use proper HTML semantics];
    D1 --> D1d[Ensure labels for form inputs];
    D1 --> D1e[Provide error messages with text];
    D1 --> D1f[Avoid using color alone to convey meaning];
    D1 --> D1g[Ensure focus is visible];

    C1 -->|Yes| E1{Does it meet WCAG AA?};

    D1 --> C1; 

    E1 -->|No| D2[Fix AA Issues];
    D2 --> D2a[Maintain sufficient contrast: 4.5 to 1 for text, 3 to 1 for UI components];
    D2 --> D2b[Ensure proper focus order];
    D2 --> D2c[Allow text resizing up to 200% without breaking];
    D2 --> D2d[Ensure consistent navigation patterns];
    D2 --> D2e[Avoid automatic content changes like auto-refreshing pages];
    D2 --> D2f[Provide captions for videos];
    D2 --> D2g[Ensure tooltips persist and are dismissible];

    E1 -->|Yes| F1{Is AAA needed for this component?};

    D2 --> E1; 

    F1 -->|No| G1[Component is WCAG AA compliant 🎉];
    F1 -->|Yes| H1[Apply AAA where possible];
    H1 --> H1a[Provide sign language interpretation for videos];
    H1 --> H1b[Increase text contrast to 7 to 1 for readability];
    H1 --> H1c[Implement live captions for audio content];
    H1 --> H1d[Avoid time limits where possible];
    H1 --> H1e[Offer multiple input methods such as voice commands];
    H1 --> H1f[Allow full customization of presentation];
    H1 --> H1g[Provide extended audio descriptions];

    H1 --> I1[Component is AAA-ready where applicable 🎉];


```