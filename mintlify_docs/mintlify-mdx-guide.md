# Mintlify MDX Complete Reference Guide

## Table of Contents
1. [Introduction](#introduction)
2. [What is Mintlify](#what-is-mintlify)
3. [What is MDX](#what-is-mdx)
4. [Frontmatter & Metadata](#frontmatter--metadata)
5. [Components Reference](#components-reference)
6. [Code Blocks](#code-blocks)
7. [Images, Tables & Embeds](#images-tables--embeds)
8. [Configuration (docs.json)](#configuration-docsjson)
9. [Best Practices](#best-practices)

---

## Introduction

This guide serves as a comprehensive reference for creating documentation using Mintlify and MDX. It covers all available components, syntax, features, and best practices for building beautiful, interactive documentation sites.

---

## What is Mintlify

Mintlify is a modern documentation platform that enables developers to create beautiful, interactive documentation websites with minimal effort. It provides:

- **Beautiful UI out of the box** - Pre-designed, responsive layouts
- **MDX support** - Write documentation using Markdown with React components
- **Interactive components** - Cards, tabs, accordions, code groups, and more
- **API documentation** - Support for OpenAPI specs and manual API docs
- **Search** - Built-in search functionality
- **GitHub integration** - Deploy directly from your repository
- **Customization** - Themes, colors, logos, and branding options

---

## What is MDX

MDX is a format that lets you seamlessly write JSX (React components) in your Markdown documents. It combines the simplicity of Markdown with the power of React components.

**Standard Markdown:**
```markdown
# Hello World
This is a paragraph.
```

**MDX with Components:**
```mdx
# Hello World
This is a paragraph.

<Note>
This is an interactive note component!
</Note>
```

---

## Frontmatter & Metadata

Frontmatter is YAML-like metadata placed at the top of your MDX files to configure page-specific settings.

### Basic Frontmatter Structure

```yaml
---
title: "Page Title"
description: "A short description for SEO and page preview"
icon: "rocket"
iconType: "solid"
---
```

### Available Frontmatter Fields

| Field | Type | Description | Example |
|-------|------|-------------|---------|
| `title` | string | The main page title (displayed at top and in sidebar) | `"Getting Started"` |
| `description` | string | SEO description and page summary | `"Learn how to get started with our platform"` |
| `sidebarTitle` | string | Shorter title for sidebar navigation | `"Get Started"` |
| `icon` | string | Icon name from Font Awesome or Lucide | `"rocket"` |
| `iconType` | string | Icon style (regular, solid, light, thin, sharp-solid, duotone, brands) | `"solid"` |
| `mode` | string | Page layout mode (default, wide, custom, center) | `"wide"` |

### Page Layout Modes

- **`default`** - Standard layout with sidebar and table of contents
- **`wide`** - Hide right-hand ToC, use full width for content
- **`custom`** - Minimal layout (no sidebar or ToC), great for landing pages
- **`center`** - Remove sidebar/ToC and center content (good for changelogs)

### Example with All Fields

```yaml
---
title: "Complete API Reference"
description: "Comprehensive guide to all API endpoints and authentication methods"
sidebarTitle: "API Reference"
icon: "code"
iconType: "duotone"
mode: "wide"
---
```

---

## Components Reference

### 1. Callouts

Callouts add eye-catching context to your content. Mintlify provides six built-in callout types plus custom callouts.

#### Built-in Callout Types

**Note** - Adds supplementary information
```mdx
<Note>
This is important information to keep in mind.
</Note>
```

**Warning** - Alerts users to potential issues
```mdx
<Warning>
Be careful when performing this operation!
</Warning>
```

**Info** - Emphasizes critical details
```mdx
<Info>
This feature is available in Pro tier and above.
</Info>
```

**Tip** - Offers helpful suggestions
```mdx
<Tip>
You can use keyboard shortcuts to speed up your workflow!
</Tip>
```

**Check** - Indicates completed or verified status
```mdx
<Check>
Your installation was successful!
</Check>
```

**Danger** - Signals serious concerns
```mdx
<Danger>
This action cannot be undone!
</Danger>
```

#### Custom Callouts

Create personalized callouts with custom icons and colors:

```mdx
<Callout icon="key" color="#FFC107" iconType="regular">
API keys are sensitive credentials. Never commit them to version control.
</Callout>
```

**Properties:**
- `icon` - Icon name (Font Awesome or Lucide)
- `color` - Hex color code (e.g., `"#FFC107"`)
- `iconType` - Icon style (regular, solid, light, etc.)

---

### 2. Card & CardGroup

Cards create clickable tiles that can link to other pages or external resources.

#### Single Card

```mdx
<Card
  title="Getting Started"
  icon="rocket"
  href="/docs/getting-started"
>
  Learn the basics and set up your first project
</Card>
```

#### CardGroup

Group multiple cards in a responsive grid:

```mdx
<CardGroup cols={2}>
  <Card
    title="Quick Start"
    icon="bolt"
    href="/quick-start"
  >
    Get up and running in 5 minutes
  </Card>

  <Card
    title="API Reference"
    icon="code"
    href="/api"
  >
    Explore our complete API documentation
  </Card>

  <Card
    title="Tutorials"
    icon="book"
    href="/tutorials"
  >
    Step-by-step guides for common tasks
  </Card>

  <Card
    title="Examples"
    icon="puzzle-piece"
    href="/examples"
  >
    Browse code examples and templates
  </Card>
</CardGroup>
```

**Properties:**
- `title` - Card heading
- `icon` - Icon name
- `iconType` - Icon style (optional)
- `href` - Link destination (internal or external)
- `cols` - Number of columns (CardGroup only): 1, 2, 3, or 4

---

### 3. Steps

Steps component displays sequential content with numbered indicators.

```mdx
<Steps>
  <Step title="Install dependencies">
    Run `npm install` to install all required packages.
  </Step>

  <Step title="Configure environment">
    Create a `.env` file with your API keys and configuration.
  </Step>

  <Step title="Start the server">
    Execute `npm start` to launch the development server.
  </Step>
</Steps>
```

**Step Properties:**
- `title` - The step heading
- `icon` - Custom icon (optional)
- `iconType` - Icon style (optional)
- `titleSize` - Size of title: `p`, `h2`, or `h3` (default: `p`)

#### Steps with Custom Icons

```mdx
<Steps>
  <Step title="Download" icon="download" iconType="solid">
    Download the latest release from GitHub.
  </Step>

  <Step title="Install" icon="gear" iconType="solid">
    Run the installer and follow the prompts.
  </Step>

  <Step title="Launch" icon="rocket" iconType="solid">
    Open the application and start using it!
  </Step>
</Steps>
```

---

### 4. Tabs

Tabs organize content into multiple panels that users can switch between.

```mdx
<Tabs>
  <Tab title="JavaScript">
    ```javascript
    const greeting = "Hello, World!";
    console.log(greeting);
    ```
  </Tab>

  <Tab title="Python">
    ```python
    greeting = "Hello, World!"
    print(greeting)
    ```
  </Tab>

  <Tab title="Ruby">
    ```ruby
    greeting = "Hello, World!"
    puts greeting
    ```
  </Tab>
</Tabs>
```

**Properties:**
- `title` - Tab label
- Any content can go inside tabs (text, code, components, etc.)

---

### 5. CodeGroup

CodeGroup creates tabbed code blocks for showing the same operation in different languages or contexts.

```mdx
<CodeGroup>

```javascript index.js
import { Configuration, OpenAIApi } from "openai";

const configuration = new Configuration({
  apiKey: process.env.OPENAI_API_KEY,
});
const openai = new OpenAIApi(configuration);
```

```python main.py
import openai

openai.api_key = os.getenv("OPENAI_API_KEY")
```

```ruby app.rb
require 'openai'

client = OpenAI::Client.new(
  access_token: ENV['OPENAI_API_KEY']
)
```

</CodeGroup>
```

**Key Points:**
- Each code block must have a filename (e.g., `index.js`, `main.py`)
- The filename becomes the tab label
- Supports all standard code block features

---

### 6. Accordion & AccordionGroup

Accordions create collapsible sections for organizing content.

#### Single Accordion

```mdx
<Accordion title="What is Mintlify?">
  Mintlify is a modern documentation platform that helps developers create beautiful, interactive documentation websites.
</Accordion>
```

#### AccordionGroup

```mdx
<AccordionGroup>
  <Accordion title="What is Mintlify?">
    Mintlify is a modern documentation platform that helps developers create beautiful, interactive documentation websites.
  </Accordion>

  <Accordion title="How does it work?">
    Mintlify uses MDX (Markdown + JSX) to let you write documentation with interactive components.
  </Accordion>

  <Accordion title="Is it free?">
    Mintlify offers both free and paid plans depending on your needs.
  </Accordion>
</AccordionGroup>
```

**Properties:**
- `title` - The accordion header text
- `icon` - Custom icon (optional)
- `defaultOpen` - Set to `true` to open by default (optional)

---

### 7. Frame

Frame wraps images or components in a container with optional caption.

```mdx
<Frame>
  ![Dashboard Screenshot](/images/dashboard.png)
</Frame>
```

#### Frame with Caption

```mdx
<Frame caption="The main dashboard view showing analytics">
  ![Dashboard Screenshot](/images/dashboard.png)
</Frame>
```

**Properties:**
- `caption` - Text displayed below the frame
- Useful for centering images and adding context

---

### 8. Icon

Display inline icons within text or standalone.

```mdx
Click the <Icon icon="gear" /> icon to open settings.
```

**Properties:**
- `icon` - Icon name (Font Awesome, Lucide, or custom SVG)
- `iconType` - Icon style (regular, solid, light, thin, sharp-solid, duotone, brands)
- `size` - Icon size in pixels (e.g., `24`)
- `color` - Hex color code (e.g., `"#FF5733"`)

#### Icon Examples

```mdx
<Icon icon="rocket" iconType="solid" size="32" color="#FF5733" />

<Icon icon="github" iconType="brands" />

<Icon icon="check-circle" iconType="duotone" color="#10b981" />
```

---

### 9. ParamField

Define parameters for APIs or functions. Automatically generates API playgrounds.

```mdx
<ParamField path="user_id" type="string" required>
  The unique identifier for the user
</ParamField>

<ParamField path="email" type="string" required>
  User's email address
</ParamField>

<ParamField path="age" type="number">
  User's age (optional)
</ParamField>

<ParamField path="preferences" type="object">
  User preference settings
</ParamField>
```

**Properties:**
- `path` or `query` or `body` - Parameter name
- `type` - Data type: `string`, `number`, `boolean`, `object`, `array` (use `[]` suffix for arrays, e.g., `string[]`)
- `required` - Boolean indicating if parameter is required
- `default` - Default value

#### Array Types

```mdx
<ParamField path="tags" type="string[]">
  Array of tag strings
</ParamField>

<ParamField path="scores" type="number[]">
  Array of numeric scores
</ParamField>
```

---

### 10. ResponseField

Define return values and response structures for APIs.

```mdx
<ResponseField name="id" type="string">
  Unique identifier for the created resource
</ResponseField>

<ResponseField name="status" type="string">
  Current status of the operation (pending, completed, failed)
</ResponseField>

<ResponseField name="created_at" type="timestamp">
  ISO 8601 timestamp of resource creation
</ResponseField>
```

**Properties:**
- `name` - Field name
- `type` - Data type
- `required` - Whether field is always present

---

### 11. Expandable

Toggle to display nested properties, great for complex object documentation.

```mdx
<Expandable title="user_object">
  <ResponseField name="id" type="string">
    User's unique identifier
  </ResponseField>

  <ResponseField name="email" type="string">
    User's email address
  </ResponseField>

  <ResponseField name="profile" type="object">
    User profile information

    <Expandable title="profile" defaultOpen>
      <ResponseField name="name" type="string">
        Full name
      </ResponseField>

      <ResponseField name="avatar_url" type="string">
        Profile picture URL
      </ResponseField>
    </Expandable>
  </ResponseField>
</Expandable>
```

**Properties:**
- `title` - The expandable section name
- `defaultOpen` - Set to `true` to show expanded by default

---

### 12. Tooltip

Show definitions when hovering over text.

```mdx
<Tooltip tip="Application Programming Interface">
  API
</Tooltip>
```

**Properties:**
- `tip` - The tooltip text to display on hover

---

## Code Blocks

Mintlify uses Shiki for syntax highlighting with support for all major programming languages.

### Basic Code Block

````markdown
```javascript
const greeting = "Hello, World!";
console.log(greeting);
```
````

### Code Block with Title

````markdown
```javascript app.js
const greeting = "Hello, World!";
console.log(greeting);
```
````

### Line Highlighting

Highlight specific lines using the `highlight` property:

````markdown
```javascript {2,4-6}
import React from 'react';
import { useState } from 'react'; // Highlighted

function App() {
  const [count, setCount] = useState(0); // Highlighted
  // These lines are highlighted

  return <div>Count: {count}</div>;
}
```
````

### Line Numbers

Display line numbers using the `showLineNumbers` property:

````markdown
```python showLineNumbers
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

print(fibonacci(10))
```
````

### Diff Visualization

Show additions and removals using `+` and `-` prefixes:

````markdown
```javascript
function calculateTotal(items) {
-  return items.reduce((sum, item) => sum + item.price, 0);
+  return items.reduce((sum, item) => sum + item.price * item.quantity, 0);
}
```
````

### Combined Features

````markdown
```typescript user.service.ts {5-7,12} showLineNumbers
import { Injectable } from '@nestjs/common';
import { User } from './user.entity';

@Injectable()
export class UserService {
  private users: User[] = [];
  // Service implementation

  async findById(id: string): Promise<User> {
    return this.users.find(user => user.id === id);
  }

  async create(userData: Partial<User>): Promise<User> {
    const user = new User(userData);
    this.users.push(user);
    return user;
  }
}
```
````

---

## Images, Tables & Embeds

### Images

#### Basic Image

```markdown
![Alt text](/images/screenshot.png)
```

#### Image with Frame and Caption

```mdx
<Frame caption="Dashboard overview showing key metrics">
  ![Dashboard](/images/dashboard.png)
</Frame>
```

#### Disable Zoom on Click

```mdx
<img src="/images/logo.png" alt="Logo" noZoom />
```

#### Light/Dark Mode Images

Use Tailwind CSS classes to show different images based on theme:

```mdx
<img src="/images/light-mode.png" className="block dark:hidden" />
<img src="/images/dark-mode.png" className="hidden dark:block" />
```

#### Linked Images

```mdx
<a href="https://example.com" target="_blank">
  <img src="/images/clickable.png" noZoom />
</a>
```

### Tables

Standard Markdown tables are supported:

```markdown
| Feature | Free | Pro | Enterprise |
|---------|------|-----|------------|
| Users | 1 | 10 | Unlimited |
| Storage | 1GB | 100GB | Unlimited |
| Support | Community | Email | 24/7 Phone |
```

### Embeds

#### YouTube Videos

```markdown
<iframe
  width="560"
  height="315"
  src="https://www.youtube.com/embed/VIDEO_ID"
  title="YouTube video player"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen
></iframe>
```

#### Other Embeds

Mintlify supports HTML, so you can embed any iframe-based content (CodePen, Figma, etc.)

---

## Configuration (docs.json)

The `docs.json` file (formerly `mint.json`) controls your Mintlify project settings.

### Basic Configuration Structure

```json
{
  "name": "My Documentation",
  "logo": {
    "light": "/logo/light.png",
    "dark": "/logo/dark.png"
  },
  "favicon": "/favicon.png",
  "colors": {
    "primary": "#0D9373",
    "light": "#07C983",
    "dark": "#0D9373"
  },
  "topbarLinks": [
    {
      "name": "GitHub",
      "url": "https://github.com/username/repo"
    }
  ],
  "topbarCtaButton": {
    "name": "Get Started",
    "url": "https://app.example.com"
  },
  "navigation": [
    {
      "group": "Getting Started",
      "pages": [
        "introduction",
        "quickstart"
      ]
    },
    {
      "group": "API Reference",
      "pages": [
        "api/authentication",
        "api/users",
        "api/errors"
      ]
    }
  ]
}
```

### Key Configuration Options

#### Theme Settings

```json
{
  "theme": "system",
  "layout": "topnav"
}
```

- `theme`: `"system"`, `"light"`, or `"dark"`
- `layout`: `"topnav"` or `"sidenav"`

#### Icon Library

```json
{
  "iconLibrary": "fontawesome"
}
```

Supported: `"fontawesome"` or `"lucide"`

#### Footer Configuration

```json
{
  "footerSocials": {
    "twitter": "https://twitter.com/username",
    "github": "https://github.com/username",
    "discord": "https://discord.gg/invite"
  }
}
```

#### API Configuration

For MDX-based API documentation:

```json
{
  "api": {
    "baseUrl": "https://api.example.com/v1",
    "auth": {
      "method": "bearer"
    }
  }
}
```

---

## Best Practices

### 1. Component Formatting

Always add blank lines around components for proper rendering:

```mdx
Regular paragraph text.

<Note>
This is a note with proper spacing.
</Note>

More paragraph text.
```

### 2. Indentation

Indent content inside components by 2 spaces:

```mdx
<Card title="Example">
  This content is properly indented.

  It maintains readability in the source code.
</Card>
```

### 3. Use Semantic Components

Choose the right component for the job:
- `<Note>` for general information
- `<Warning>` for cautionary advice
- `<Tip>` for helpful suggestions
- `<Danger>` for critical warnings

### 4. Code Organization

- Use CodeGroup for multi-language examples
- Add filenames to code blocks for context
- Highlight important lines
- Use line numbers for longer code blocks

### 5. Navigation Structure

Organize your docs.json navigation logically:
- Group related pages together
- Use clear, descriptive group names
- Order pages from basic to advanced
- Limit nesting depth for better UX

### 6. SEO Optimization

- Always include `title` and `description` in frontmatter
- Use descriptive, keyword-rich titles
- Keep descriptions concise (150-160 characters)
- Use proper heading hierarchy (H1 → H2 → H3)

### 7. Icons

- Use icons consistently across similar page types
- Stick to one icon library (Font Awesome or Lucide)
- Choose icons that clearly represent the content
- Use `iconType` consistently for visual coherence

### 8. Images

- Optimize images before uploading (compress, resize)
- Use descriptive alt text for accessibility
- Provide light/dark mode variants when needed
- Use Frame component for important screenshots

### 9. API Documentation

- Use ParamField for all parameters
- Include type information
- Mark required fields clearly
- Provide examples for complex objects
- Use Expandable for nested structures

### 10. Accessibility

- Provide alt text for all images
- Use semantic HTML
- Maintain proper heading hierarchy
- Ensure sufficient color contrast
- Test with keyboard navigation

---

## VSCode Extension

Install the **Mintlify MDX** extension for enhanced development experience:

**Features:**
- Snippets for all Mintlify components
- Syntax highlighting for MDX
- Auto-completion for component props
- Preview functionality

**Snippets:**
- `note` → Note component
- `warning` → Warning component
- `tip` → Tip component
- `card` → Card component
- `steps` → Steps component
- And many more...

---

## Additional Resources

- **Official Documentation**: https://mintlify.com/docs
- **GitHub Repository**: https://github.com/mintlify/docs
- **Community Discord**: Join for support and discussions
- **Examples**: Browse the Mintlify showcase for inspiration

---

## Quick Reference Cheat Sheet

### Components

```mdx
<Note>Information</Note>
<Warning>Caution</Warning>
<Tip>Helpful advice</Tip>

<Card title="Title" icon="icon-name" href="/link">Content</Card>

<Steps>
  <Step title="Title">Content</Step>
</Steps>

<Tabs>
  <Tab title="Title">Content</Tab>
</Tabs>

<CodeGroup>
```lang filename
code
```
</CodeGroup>

<Accordion title="Title">Content</Accordion>

<Frame caption="Caption">![Alt](/image.png)</Frame>

<Icon icon="name" size="24" color="#000" />

<ParamField path="name" type="string" required>Description</ParamField>

<ResponseField name="name" type="string">Description</ResponseField>

<Expandable title="object">Nested fields</Expandable>

<Tooltip tip="Definition">Term</Tooltip>
```

### Frontmatter

```yaml
---
title: "Page Title"
description: "Page description"
sidebarTitle: "Short Title"
icon: "icon-name"
iconType: "solid"
mode: "wide"
---
```

---

**End of Mintlify MDX Reference Guide**
