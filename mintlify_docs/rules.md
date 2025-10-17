# Mintlify MDX Documentation Rules

This document defines the rules and guidelines to follow when creating Mintlify MDX documentation files for Freiya. These rules ensure consistency, quality, and maintainability across all documentation.

---

## 1. Text Formatting & Capitalization

### 1.1 Sentence Case Only
- **ALWAYS use Sentence case** - Only capitalize the first letter of sentences and proper nouns
- **NEVER use PascalCase, Title Case, or ALL CAPS** in headings or regular text
- Proper nouns, product names, and acronyms are exceptions

**Examples:**
```markdown
✅ CORRECT:
# Getting started with Freiya
## How to add papers to your library
### Understanding AI chat features

❌ INCORRECT:
# Getting Started With Freiya
# GETTING STARTED WITH FREIYA
## How To Add Papers To Your Library
```

### 1.2 Proper Nouns & Product Names
Always capitalize correctly:
- Freiya (product name)
- Mintlify (product name)
- OpenAI, Google AI (company/product names)
- PDF, API, URL, DOI, JSON (acronyms)
- LangChain, PostgreSQL, Supabase (technology names)

---

## 2. Images & Visual Assets

### 2.1 Image Placeholders
When an image is needed, use this exact format:

```markdown
++IMAGE: **Clear description of what the image should show**++
```

**Guidelines for image descriptions:**
- Be specific about what should be shown
- Include UI elements that should be visible
- Mention any highlights, arrows, or annotations needed
- Specify the context (which page/feature)

**Examples:**
```markdown
✅ GOOD:
++IMAGE: **Screenshot of the paper library showing the "Add Paper" button highlighted in the top-right corner, with 3-4 sample papers visible in the list view**++

++IMAGE: **Diagram showing the AI chat workflow: user input → LangChain processing → model selection → streaming response, with arrows connecting each step**++

❌ BAD:
++IMAGE: **Add paper button**++
++IMAGE: **Screenshot**++
```

### 2.2 Image Placement
- Place images immediately after the paragraph that references them
- Always provide context before showing an image
- Include a caption when the image needs it (using Frame component)

---

## 3. Writing Style & Tone

### 3.1 Voice & Perspective
- **Use second person "you"** when addressing the reader
- Avoid "we" (unless referring to Freiya team in specific contexts)
- Avoid "one" or impersonal constructions
- Be direct and conversational

**Examples:**
```markdown
✅ CORRECT:
You can add papers using the DOI search feature.
To create a collection, click the "New Collection" button.

❌ INCORRECT:
We can add papers using the DOI search feature.
One can create a collection by clicking...
Users will be able to add papers...
```

### 3.2 Active Voice
- Prefer active voice over passive voice
- Make instructions clear and direct
- Focus on what the user does, not what happens

**Examples:**
```markdown
✅ ACTIVE:
Click "Add Paper" to open the dialog.
The system fetches metadata from Semantic Scholar.

❌ PASSIVE:
The dialog is opened by clicking "Add Paper".
Metadata is fetched from Semantic Scholar by the system.
```

### 3.3 Tone
- **Professional but approachable** - Not too formal, not too casual
- **Helpful and encouraging** - Guide users positively
- **Clear and concise** - No unnecessary jargon
- **Confident** - Use definitive language, avoid "might" or "maybe" unless truly uncertain

**Examples:**
```markdown
✅ GOOD TONE:
Freiya makes academic research easier by organizing your papers and providing AI-powered insights.

❌ TOO FORMAL:
Freiya facilitates the optimization of scholarly research activities through systematic organization and AI-enabled analytical capabilities.

❌ TOO CASUAL:
Freiya is like, super cool for organizing your papers and stuff!
```

---

## 4. Component Usage Guidelines

### 4.1 Callout Selection

**Use callouts strategically** - Don't overuse them. Follow these guidelines:

| Callout | When to Use | Example |
|---------|-------------|---------|
| `<Note>` | Supplementary information, helpful context | "Note: Free tier users can add up to 5 papers" |
| `<Tip>` | Best practices, pro tips, suggestions | "Tip: Use keyboard shortcuts to speed up your workflow" |
| `<Info>` | Important information that affects usage | "Info: This feature is available in Pro tier and above" |
| `<Warning>` | Caution about potential issues | "Warning: Deleting a collection cannot be undone" |
| `<Danger>` | Critical warnings, data loss risks | "Danger: This will permanently delete your account and all data" |
| `<Check>` | Successful completion, verification | "Check: Your email has been verified successfully" |

**Callout Rules:**
- Maximum 2-3 callouts per page section
- Don't stack callouts (avoid multiple in a row)
- Keep callout content brief (1-3 sentences)
- Add blank lines before and after callouts

### 4.2 Cards & CardGroups

**When to use Cards:**
- Navigation to related topics
- Feature highlights
- Link collections
- Getting started guides

**CardGroup Rules:**
- Use 2-4 cards per group (preferably 2 or 3)
- Keep card titles short (2-5 words)
- Card descriptions should be one sentence
- All cards in a group should be related

### 4.3 Steps Component

**Use Steps for:**
- Sequential procedures
- Setup guides
- Workflows with clear order
- Numbered instructions

**Steps Rules:**
- Minimum 2 steps, maximum 10
- Each step should be actionable
- Use brief titles (3-7 words)
- Include detailed content within each step

### 4.4 Tabs & CodeGroups

**Use Tabs for:**
- Different user paths
- Platform-specific instructions
- Multiple approaches to same task

**Use CodeGroup for:**
- Multi-language code examples
- Same operation in different contexts
- Alternative implementations

### 4.5 Accordions

**Use Accordions for:**
- FAQ sections
- Optional advanced information
- Collapsible reference material
- Long lists that would clutter the page

**Avoid Accordions for:**
- Critical information users need to see
- Short content (< 2 sentences)
- Primary instructions

---

## 5. Code Block Standards

### 5.1 Always Specify Language
Every code block MUST include a language identifier:

```markdown
✅ CORRECT:
```javascript
const example = "code";
```

❌ INCORRECT:
```
const example = "code";
```
```

### 5.2 Include Filenames When Relevant
Add filenames to provide context:

````markdown
```javascript app.js
import React from 'react';
```

```python main.py
import openai
```
````

### 5.3 Code Example Quality
- **Use realistic examples** - Not "foo", "bar", "baz"
- **Working code** - Examples should be functional
- **Consistent naming** - Use meaningful variable names
- **Comments** - Add comments to explain complex parts
- **Format properly** - Consistent indentation and style

**Examples:**
```markdown
✅ GOOD:
```javascript
// Fetch paper metadata from DOI
const paper = await fetchPaperByDOI("10.1234/example.doi");
console.log(paper.title);
```

❌ BAD:
```javascript
var x = foo("bar");
console.log(x.y);
```
```

### 5.4 Line Highlighting
- Use sparingly - only for important lines
- Highlight 3-5 lines maximum
- Explain why lines are highlighted

---

## 6. Heading Structure & Hierarchy

### 6.1 Heading Levels
- **One H1 per page** - The page title (from frontmatter)
- **Logical hierarchy** - Don't skip levels (H2 → H4 is wrong)
- **Maximum depth of H3** - Rarely use H4, never beyond
- **Descriptive headings** - Clear, specific, searchable

**Correct hierarchy:**
```markdown
# Page title (H1 - from frontmatter)
## Main section (H2)
### Subsection (H3)
### Another subsection (H3)
## Another main section (H2)
```

### 6.2 Heading Style
- Use sentence case (rule #1)
- Keep headings concise (3-8 words)
- Make them descriptive and scannable
- Use parallel structure in sibling headings

**Examples:**
```markdown
✅ GOOD:
## Adding papers to your library
### Search by DOI
### Manual entry
### Upload PDF

❌ BAD:
## Papers
### DOI
### You can also enter manually
### Uploading
```

---

## 7. Links & Cross-References

### 7.1 Internal Links
- Use relative paths for internal links
- Link to related pages when relevant
- Use descriptive link text (not "click here")

**Format:**
```markdown
See [paper management](/features/papers) for more details.
Learn how to [create collections](/features/collections).
```

### 7.2 External Links
- Always include `target="_blank"` for external links (or use Mintlify's auto-handling)
- Link to official documentation when referencing tools
- Keep external links up to date

### 7.3 Link Text
```markdown
✅ GOOD:
Learn more about [DOI identifiers](https://www.doi.org/).
See the [OpenAI API documentation](https://platform.openai.com/docs).

❌ BAD:
Click [here](https://www.doi.org/) to learn about DOI.
More info [here](https://platform.openai.com/docs).
```

---

## 8. Frontmatter Standards

### 8.1 Required Fields
Every MDX file MUST include:
```yaml
---
title: "Page title in sentence case"
description: "Brief, clear description for SEO (120-160 characters)"
---
```

### 8.2 Optional Fields
Include when appropriate:
```yaml
---
title: "Page title"
description: "Page description"
icon: "icon-name"
iconType: "solid"
mode: "wide"
sidebarTitle: "Short title"
---
```

### 8.3 Frontmatter Guidelines
- **title**: Sentence case, descriptive, unique
- **description**: One sentence, include key terms, 120-160 chars
- **icon**: Use relevant, consistent icons
- **mode**: Only use "wide" or "custom" when needed
- **sidebarTitle**: Use for long titles that need shortening

---

## 9. Lists & Tables

### 9.1 Unordered Lists
Use for:
- Items without specific order
- Features, benefits, options
- Related but independent items

**Rules:**
- Use `-` for bullets (consistent with Markdown standard)
- Keep items parallel in structure
- Don't exceed 2 levels of nesting

### 9.2 Ordered Lists
Use for:
- Sequential steps (or use Steps component)
- Ranked items
- Prioritized lists

**Rules:**
- Start with `1.` (Markdown auto-numbers)
- Each item should be complete sentence or parallel phrase
- Use Steps component for procedures (preferred over ordered lists)

### 9.3 Tables
Use for:
- Comparing options
- Feature matrices
- Reference data
- Specifications

**Rules:**
- Include header row
- Keep cells concise
- Use consistent formatting
- Align columns appropriately
- Maximum 5-6 columns for readability

**Example:**
```markdown
| Feature | Free | Pro | Nova |
|---------|------|-----|------|
| Papers | 5 | 500 | 500 |
| Collections | 2 | 20 | 20 |
| AI models | Basic | Advanced | Specialized |
```

---

## 10. Content Organization

### 10.1 Page Length
- **Ideal**: 500-1500 words per page
- **Maximum**: 2500 words
- **If longer**: Break into multiple pages
- **Navigation**: Use table of contents for pages > 1000 words

### 10.2 Section Structure
Each page should follow this structure:
1. **Introduction paragraph** - What this page covers
2. **Main content** - Organized with H2/H3 headings
3. **Related links** (optional) - Links to related topics
4. **Next steps** (optional) - What to read next

### 10.3 Content Density
- One main idea per paragraph
- Paragraphs of 2-4 sentences
- Use white space effectively
- Break up long sections with headings, lists, or components

---

## 11. Accessibility

### 11.1 Alt Text for Images
When images are added (replacing placeholders), they MUST include alt text:
```markdown
![Clear description of what the image shows](/path/to/image.png)
```

### 11.2 Semantic HTML
- Use proper heading hierarchy (no skipping levels)
- Use lists for list content
- Use tables for tabular data
- Don't use formatting for semantic meaning

### 11.3 Link Clarity
- Links should make sense out of context
- Avoid "click here" or "learn more" without context
- Describe the destination

---

## 12. Technical Accuracy

### 12.1 Verification
Before documenting:
- ✅ Test all code examples
- ✅ Verify all procedures work
- ✅ Check API endpoints are correct
- ✅ Validate data and statistics
- ✅ Confirm feature availability by tier

### 12.2 Version Information
- Note if feature is "Coming Soon"
- Specify tier requirements clearly
- Mark deprecated features
- Update when features change

### 12.3 Examples & Data
- Use realistic examples
- Don't expose real API keys or sensitive data
- Use placeholder data that looks real
- Example emails: `user@example.com`
- Example DOIs: `10.1234/example.doi`
- Example URLs: `https://example.com`

---

## 13. Special Formatting

### 13.1 Bold Text
Use bold for:
- **Emphasis** on critical points
- **UI element names** (buttons, menu items)
- **First mention** of key terms in a section

**Examples:**
```markdown
Click the **Add Paper** button in the top-right corner.
The **Free tier** includes 5 papers.
```

### 13.2 Italic Text
Use italics for:
- *Subtle emphasis*
- *Term definitions* when first introduced
- *Variables* or *parameters* in prose

**Examples:**
```markdown
A *collection* is a group of related papers.
Set the *user_id* parameter to your account ID.
```

### 13.3 Inline Code
Use backticks for:
- `Code elements` in text
- `API endpoints`
- `File names` and `paths`
- `Command` names
- `Variable names`
- `Function names`

**Examples:**
```markdown
Run the `npm install` command.
The `user_id` field is required.
Edit the `.env` file.
Call the `/api/papers` endpoint.
```

### 13.4 Keyboard Keys
Use code formatting for keyboard shortcuts:
```markdown
Press `Ctrl + K` to open quick search.
Use `Enter` to submit the form.
```

---

## 14. Examples & Scenarios

### 14.1 Real-World Examples
- Use realistic scenarios
- Reference actual use cases
- Provide complete context
- Show expected outcomes

**Example:**
```markdown
✅ GOOD:
Suppose you're working on your thesis and need to organize papers for Chapter 2
on "Machine Learning in Healthcare". You can create a collection called
"Thesis - Chapter 2 - ML Healthcare" and add relevant papers to it.

❌ BAD:
You can create a collection and add papers.
```

### 14.2 Step-by-Step Walkthroughs
- Include context (starting point)
- Show each action clearly
- Explain what happens at each step
- Confirm the end result

---

## 15. Consistency Checklist

Before finalizing any MDX file, verify:

- [ ] All headings use sentence case
- [ ] Second person "you" used throughout
- [ ] Active voice in instructions
- [ ] Image placeholders follow format: `++IMAGE: **description**++`
- [ ] All code blocks have language specified
- [ ] Frontmatter includes required fields
- [ ] No callout overuse (max 2-3 per section)
- [ ] Links use descriptive text
- [ ] Tables are well-formatted
- [ ] Heading hierarchy is logical (no skipping)
- [ ] Technical accuracy verified
- [ ] Examples are realistic and working
- [ ] Tone is professional but approachable
- [ ] Content length is appropriate (500-2500 words)
- [ ] Related topics are linked

---

## 16. File Naming & Organization

### 16.1 File Names
- Use lowercase with hyphens: `getting-started.mdx`
- Be descriptive but concise: `paper-management.mdx`
- Match the main topic: `ai-chat.mdx`

### 16.2 Directory Structure
Organize files logically:
```
docs/
├── getting-started/
│   ├── introduction.mdx
│   ├── signup.mdx
│   └── first-steps.mdx
├── features/
│   ├── ai-chat.mdx
│   ├── paper-management.mdx
│   ├── collections.mdx
│   └── pdf-viewer.mdx
├── guides/
│   ├── research-workflow.mdx
│   └── organizing-papers.mdx
└── reference/
    ├── keyboard-shortcuts.mdx
    └── subscription-tiers.mdx
```

---

## 17. Review Process

### 17.1 Self-Review
Before submitting, review for:
1. Rule compliance (this document)
2. Spelling and grammar
3. Technical accuracy
4. Link validity
5. Code functionality
6. Consistent formatting

### 17.2 Peer Review
If possible, have another person:
- Read for clarity
- Test procedures
- Check for completeness
- Verify examples work

---

## Quick Reference

**Essential Rules:**
1. ✅ Sentence case only
2. ✅ Image placeholders: `++IMAGE: **description**++`
3. ✅ Second person "you"
4. ✅ Active voice
5. ✅ Specify language in code blocks
6. ✅ Required frontmatter: title, description
7. ✅ Descriptive link text
8. ✅ Max 2-3 callouts per section
9. ✅ Logical heading hierarchy
10. ✅ Verify technical accuracy

**Common Mistakes to Avoid:**
- ❌ Title Case In Headings
- ❌ "We can do this..." (use "You can do this...")
- ❌ Code blocks without language
- ❌ "Click here" links
- ❌ Skipping heading levels
- ❌ Too many callouts
- ❌ Passive voice in instructions
- ❌ Vague image descriptions

---

**Last Updated:** January 2025
**Version:** 1.0
