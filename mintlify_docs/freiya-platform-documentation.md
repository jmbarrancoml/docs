# Freiya Platform - Complete Documentation

## Table of Contents

1. [Platform Overview](#platform-overview)
2. [Technology Stack](#technology-stack)
3. [Getting Started](#getting-started)
4. [AI Chat System](#ai-chat-system)
5. [Paper Management](#paper-management)
6. [Collections](#collections)
7. [PDF Viewer & Annotations (Focus)](#pdf-viewer--annotations-focus)
8. [Institution Search](#institution-search)
9. [Subscription & Tiers](#subscription--tiers)
10. [Settings & Preferences](#settings--preferences)
11. [Admin Tools](#admin-tools)
12. [Keyboard Shortcuts](#keyboard-shortcuts)
13. [Tips & Best Practices](#tips--best-practices)

---

## Platform Overview

### What is Freiya?

Freiya is an AI-powered academic research assistant platform designed to help researchers, students, and academics streamline their research workflow. It combines advanced AI capabilities with powerful paper management tools to create a comprehensive research companion.

### Core Mission

Freiya aims to make academic research more accessible, organized, and efficient by providing:
- **Intelligent AI assistance** for research queries and paper analysis
- **Comprehensive paper management** for organizing research materials
- **Advanced annotation tools** for deep paper reading and analysis
- **Collaborative features** for sharing insights and conversations
- **Multi-language support** for global accessibility

### Key Features at a Glance

| Feature | Description |
|---------|-------------|
| **AI Chat** | Multi-model AI conversations with context awareness |
| **Paper Library** | Organize and manage research papers with metadata |
| **Collections** | Group papers and chats into organized collections |
| **PDF Viewer** | Read, highlight, and annotate papers (Focus mode) |
| **Institution Search** | Track and explore academic institutions |
| **Smart Search** | Vector-based semantic search across papers |
| **Citation Management** | Generate citations in multiple formats |
| **Subscription Tiers** | Flexible plans from Free to Unlimited |

### Target Users

- **Academic Researchers** - Manage large paper libraries and conduct literature reviews
- **Graduate Students** - Organize thesis research and track citations
- **Professors** - Curate reading lists and share resources
- **Research Teams** - Collaborate on shared research projects
- **Independent Scholars** - Access powerful research tools affordably

---

## Technology Stack

### Frontend Technologies

- **React 18.3.1** - Modern UI library for building interactive interfaces
- **React Router 6.30** - Client-side routing and navigation
- **Tailwind CSS 3.4** - Utility-first CSS framework for styling
- **Framer Motion 11.18** - Animation library for smooth transitions
- **Material-UI (MUI) 6.1** - Component library for consistent UI elements
- **TipTap 2.12** - Rich text editor for notes and annotations
- **React PDF** - PDF viewing and rendering capabilities
- **Chart.js 4.4** - Data visualization for analytics
- **Axios** - HTTP client for API requests
- **React Hot Toast** - Beautiful notification system

### Backend Technologies

- **Node.js with Express 4.21** - Server framework
- **PostgreSQL** - Primary database for user data and metadata
- **Supabase** - Backend-as-a-Service for auth and database management
- **JWT (jsonwebtoken)** - Secure authentication tokens
- **Bcrypt** - Password hashing and security
- **Multer** - File upload handling
- **Nodemailer** - Email sending for verification and notifications
- **PDF-Parse** - PDF text extraction

### AI & Machine Learning

- **LangChain 0.3** - Framework for building LLM applications
- **OpenAI GPT Models** - Primary AI capabilities
- **Google Generative AI** - Alternative AI provider
- **Hugging Face Transformers** - Local embeddings generation
- **FastEmbed** - Fast embedding generation for vector search

### Vector Databases

- **Qdrant** - Primary vector database for semantic search
- **Pinecone** - Alternative vector store option
- **ChromaDB** - Local vector database support

### Payment & Billing

- **Stripe** - Payment processing and subscription management
- **DodoPayments** - Additional payment provider integration

### Authentication & Security

- **Passport.js** - Authentication middleware
- **Google OAuth 2.0** - Social login integration
- **Express Session** - Session management
- **Cookie Parser** - Cookie handling
- **CORS** - Cross-origin resource sharing configuration

### Developer Tools

- **React App Rewired** - Custom webpack configuration
- **Terser** - JavaScript minification
- **Autoprefixer** - CSS vendor prefixing
- **ESLint** - Code linting
- **Cross-env** - Environment variable management

---

## Getting Started

### Sign Up Process

Freiya offers two registration methods:

#### 1. Email Registration

**Steps:**
1. Navigate to the signup page at `/auth/signup`
2. Enter your name, email, and password
3. Click "Sign Up"
4. Check your email for a verification code
5. Enter the 5-digit code on the verification page
6. Account is activated upon successful verification

**Email Verification:**
- Verification codes are valid for 1 hour
- Codes are sent immediately upon registration
- Check spam folder if email doesn't arrive
- Request a new code if expired

**Password Requirements:**
- Minimum length requirements enforced
- Hashed using bcrypt for security
- Can be reset via "Forgot Password" flow

#### 2. Google OAuth

**Steps:**
1. Click "Continue with Google" button
2. Select your Google account
3. Grant permissions to Freiya
4. Automatically redirected to the app
5. Account created and logged in instantly

**Benefits:**
- Faster signup process
- No password to remember
- Automatic email verification
- Secure Google authentication

### First Login Experience

Upon first login, users are:
1. Redirected to the main chat interface
2. Shown a welcome message or tutorial (optional)
3. Given access to default features based on Free tier
4. Able to explore the platform and add their first paper

### Account Setup Checklist

- ✅ Verify email address
- ✅ Set display name and preferences
- ✅ Choose language (English or Spanish)
- ✅ Select dark mode preference
- ✅ Add first research paper
- ✅ Create first collection
- ✅ Try AI chat feature
- ⚡ Consider upgrading to Pro for more features

---

## AI Chat System

### Overview

Freiya's AI chat system is the core of the platform, providing intelligent assistance for research queries, paper analysis, and academic discussions. It uses LangChain to orchestrate multiple AI models with context awareness and memory.

### Available AI Models

Freiya supports multiple AI model types, each with different capabilities and usage limits:

| Model Type | Description | Use Case | Tier Access |
|------------|-------------|----------|-------------|
| **Standard Models** | General-purpose AI | Everyday research questions | All tiers |
| **Advanced Models** | More capable reasoning | Complex analysis tasks | Pro and above |
| **Specialized Models** | Domain-specific | Specific research areas | Nova and above |

### Model Usage Tracking

**Usage System:**
- Each user has a monthly message allocation per model type
- Usage resets monthly based on subscription tier
- Real-time tracking shows remaining messages
- Usage history is stored for analytics

**Database Schema:**
```sql
user_model_usage:
  - user_id
  - model_type_id
  - total_messages (monthly allocation)
  - messages_used (current usage)
  - messages_left (calculated)
  - is_unlimited (boolean)
  - reset_date
  - next_reset_date
  - update_rate (monthly/weekly)
```

**Usage History:**
Every message sent is logged with:
- Model type used
- Chat ID
- Token count (if available)
- Timestamp

### Chat Interface Features

**Message Types:**
- **User Messages** - Questions and prompts from users
- **Assistant Messages** - AI-generated responses
- **System Messages** - Context and instructions (hidden from UI)

**Message Display:**
- Markdown rendering with syntax highlighting
- LaTeX math equation support (KaTeX)
- Code blocks with language detection
- Tables, lists, and formatted text
- Inline citations and references
- Copy-to-clipboard functionality

**Message Actions:**
- Copy message content
- Regenerate response
- Edit user message
- Delete message
- Vote thumbs up/down for feedback
- View sources (if applicable)

### Chat Management

**Creating Chats:**
1. Click "New Chat" button
2. Optionally select a model
3. Start typing your first message
4. Chat is auto-saved with generated title

**Chat Features:**
- **Auto-generated Titles** - AI creates descriptive titles from first message
- **Manual Rename** - Edit chat title anytime
- **Pin Chats** - Keep important chats at the top
- **Tags** - Organize chats with custom tags
- **Search** - Find chats by title or content
- **Delete** - Remove unwanted chats permanently

**Chat Metadata:**
```sql
chats:
  - id (UUID)
  - user_id
  - title
  - messages (JSONB array)
  - created_at
  - updated_at
  - is_pinned
  - model
  - tags (array)
  - paper_id (optional link to paper)
  - paper_title
```

### Chat History

**Sidebar Navigation:**
- Chronological list of all chats
- Grouped by date (Today, Yesterday, Last 7 Days, etc.)
- Pinned chats shown at top
- Quick search/filter
- Infinite scroll for large histories

**Chat View Page:**
Located at `/chats`, shows:
- Grid or list view of all chats
- Filter by tags, date, model
- Sort by date, title, or relevance
- Bulk actions (delete, tag, export)

### Sharing Conversations

**Share Feature:**
- Generate shareable link for any chat
- Creates read-only public view
- Tracks view count
- Can be deactivated anytime
- Access token-based security

**Shared Chat Schema:**
```sql
shared_chats:
  - id (UUID)
  - original_chat_id
  - title
  - messages (JSONB snapshot)
  - shared_by (user_id)
  - shared_at
  - access_token
  - views_count
  - is_active
```

**Share Process:**
1. Open chat to share
2. Click "Share" button
3. System generates unique URL
4. Copy link to share with others
5. Recipients can view chat without login
6. Owner can deactivate share anytime

### Context & Memory

**Conversation Context:**
- Full chat history maintained in session
- LangChain manages context window
- Automatic message trimming for long chats
- Relevant history sent with each request

**Message Trimming:**
Uses LangChain's `trimMessages` to:
- Keep recent messages
- Preserve system context
- Respect token limits
- Maintain conversation coherence

**Paper Context (Optional):**
- Chats can be linked to specific papers
- Paper metadata included in system context
- Enables paper-specific questions
- Improves relevance of responses

### Streaming Responses

**Real-time Streaming:**
- Uses Vercel AI SDK for streaming
- Responses appear word-by-word
- Better user experience
- Lower perceived latency
- Can be cancelled mid-stream

**Technical Implementation:**
```javascript
streamText({
  model: google('gemini-pro'),
  messages: conversationHistory,
  onFinish: (result) => {
    // Save complete message to database
  }
})
```

### Response Rendering

**ResponseRenderer Component:**
The platform uses a sophisticated ResponseRenderer that handles:

**Supported Formats:**
- Markdown with GFM (GitHub Flavored Markdown)
- Code blocks with syntax highlighting
- Tables
- Lists (ordered and unordered)
- Blockquotes
- LaTeX math (inline and block)
- Links and images
- HTML (sanitized)

**Special Features:**
- **Citations** - Formatted academic citations
- **Code Highlighting** - 100+ language support
- **Math Rendering** - KaTeX for equations
- **Mermaid Diagrams** - Flowcharts and diagrams
- **Collapsible Sections** - For long responses
- **Copy Buttons** - On code blocks
- **Dark Mode Support** - Adapts to theme

### Chat Collections

Users can organize chats into collections for better organization:

**Collection Features:**
- Create custom collections
- Add chats to multiple collections
- Collection descriptions and colors
- Collection-based filtering
- Count of chats per collection
- Tier-based limits

**Collection Schema:**
```sql
chat_collections:
  - id (UUID)
  - user_id
  - name
  - description
  - color
  - created_at
  - updated_at

chat_collection_relationships:
  - chat_id
  - collection_id
  - added_at
```

**Collection Limits:**
- Free: 2 chat collections
- Pro/Nova: 20 chat collections
- Unlimited: No limit

### Error Handling

**Error Types:**
- **Rate Limiting** - Too many requests
- **Model Unavailable** - Service down
- **Invalid Input** - Malformed requests
- **Authentication** - Session expired
- **Usage Exceeded** - Out of messages

**Error Display:**
- User-friendly error messages
- Suggested actions
- Retry options
- Support contact info

### Best Practices

**For Users:**
- Be specific in questions
- Provide context when needed
- Use appropriate model for task
- Break complex queries into steps
- Save important chats
- Organize with collections

**For Research:**
- Link chats to papers when relevant
- Use paper context for better answers
- Export important conversations
- Share insights with collaborators
- Track citation information

---

## Paper Management

### Overview

Freiya's paper management system allows researchers to build and organize their personal library of academic papers. Papers can be added from various sources, enriched with metadata, and organized using collections and tags.

### Adding Papers

Freiya supports multiple methods for adding papers to your library:

#### 1. DOI Search

**What is DOI?**
Digital Object Identifier - a unique identifier for academic publications.

**How to Add via DOI:**
1. Click "Add Paper" button
2. Select "Search by DOI" option
3. Enter DOI (e.g., `10.1234/example.doi`)
4. System automatically fetches metadata
5. Review and confirm paper details
6. Paper added to library

**Metadata Retrieved:**
- Title
- Authors and affiliations
- Publication name
- Publication year
- Abstract
- Citation count
- PDF URL (if available via open access)
- DOI and URL links
- Institutions

**Data Sources:**
- Semantic Scholar API
- CrossRef API
- OpenAlex API (fallback for institutions)

#### 2. Manual Entry

**When to Use:**
- Paper doesn't have a DOI
- Metadata is incomplete or incorrect
- Adding historical papers
- Preprints and unpublished work

**Manual Fields:**
- Title (required)
- Authors
- Publication name
- Year
- Abstract
- Tags
- Notes
- DOI (optional)
- URL (optional)

#### 3. PDF Upload

**Upload Process:**
1. Select "Upload PDF" option
2. Choose PDF file from device
3. System extracts text and metadata
4. Auto-fills available fields
5. Review and edit details
6. Save to library

**PDF Processing:**
- Text extraction using pdf-parse
- Metadata extraction from PDF properties
- File stored securely
- File size limit based on tier

### Paper Metadata

Each paper in your library contains comprehensive metadata:

**Core Fields:**
```sql
papers:
  - id (UUID)
  - user_id
  - paper_id (Semantic Scholar ID or custom)
  - title
  - authors (text)
  - publication
  - year
  - abstract
  - tags (array)
  - notes (text)
  - citations (count)
  - doi
  - url
  - created_at
  - updated_at
```

**Metadata Display:**
- Full author list with affiliations
- Publication venue and date
- Citation count (updated)
- Abstract with expand/collapse
- Links to original source
- PDF access (if available)
- Tags and notes

### Tags & Organization

**Tagging System:**
- Add multiple tags per paper
- Create tags on-the-fly
- Filter library by tags
- Tag suggestions based on content
- Rename or merge tags
- Delete unused tags

**Common Tag Examples:**
- Research areas (e.g., "machine learning", "bioinformatics")
- Project names (e.g., "thesis", "grant-proposal")
- Reading status (e.g., "to-read", "read", "review")
- Importance (e.g., "key-paper", "reference")

### Notes & Annotations

**Paper Notes:**
- Rich text editor for detailed notes
- Markdown support
- Auto-save functionality
- Timestamped
- Searchable
- Export with paper

**Use Cases:**
- Summary of key findings
- Methodology notes
- Critical analysis
- Connection to other papers
- Questions for further research
- Personal insights

### Search & Filters

**Library Search:**
- Full-text search across title, authors, abstract
- Tag-based filtering
- Year range filters
- Publication venue filtering
- Citation count sorting
- Date added sorting

**Search Features:**
- Real-time results
- Highlight matching terms
- Advanced boolean operators
- Saved searches (future feature)
- Search history

### Paper Detail View

**Comprehensive Paper Page:**
Located at `/paper/:paperId`, displays:

**Header Section:**
- Paper title
- Authors with institution links
- Publication info (venue, year)
- Citation count
- Open access indicators
- Action buttons (View PDF, Cite, Share, Delete)

**Content Tabs:**
1. **Overview** - Abstract, key information
2. **Details** - Full metadata, DOI, URLs
3. **Notes** - User's notes and annotations
4. **Highlights** - PDF annotations (if any)
5. **Collections** - Collections containing this paper
6. **Related** - Similar papers (future feature)

**Actions Available:**
- View full-text PDF (if available)
- Add to collections
- Edit metadata
- Add/edit notes
- Generate citations
- Share paper link
- Delete from library

### Citations & Export

**Citation Formats Supported:**
- APA (American Psychological Association)
- MLA (Modern Language Association)
- Chicago
- Harvard
- IEEE
- BibTeX
- RIS

**Citation Features:**
- One-click copy to clipboard
- Export multiple papers at once
- Download as .bib or .ris file
- Integration with reference managers
- Custom citation styles (future)

**Export Process:**
1. Select papers to export
2. Choose citation format
3. Click "Export Citations"
4. Download file or copy to clipboard
5. Import into reference manager

### Paper Limits by Tier

**Storage Limits:**
| Tier | Max Papers | Papers/Month |
|------|------------|--------------|
| Free | 5 | 5 |
| Pro | 500 | 500 |
| Nova | 500 | 500 |
| Unlimited | ∞ | ∞ |

**Monthly Limits:**
- Reset on the 1st of each month
- Prevents accidental bulk imports
- Protects database resources
- Can be increased on higher tiers

**Limit Enforcement:**
- Warning at 80% capacity
- Error when limit reached
- Upgrade prompt
- Suggestion to delete old papers

### Paper Management Actions

**Bulk Operations:**
- Select multiple papers
- Add to collection
- Apply tags
- Export citations
- Delete selected

**Individual Actions:**
- Edit metadata
- Update tags
- Add to collections
- Remove from collections
- View PDF
- Generate citation
- Share link
- Delete

### Integration with Other Features

**Paper-Linked Chats:**
- Start chat about specific paper
- Paper context included in AI responses
- Access from paper detail page
- Chat shows in paper history

**Paper Highlights:**
- View highlights in paper detail
- Filter by color or category
- Export annotations
- Link to specific pages

**Institution Links:**
- Click author institution
- View institution page
- See related papers
- Track institutional research

---

## Collections

### Overview

Collections in Freiya allow you to organize your research materials into logical groups. There are two types of collections: **Paper Collections** and **Chat Collections**.

### Paper Collections

**Purpose:**
Organize research papers by topic, project, course, or any custom category.

**Use Cases:**
- Literature review for thesis chapter
- Papers for grant proposal
- Reading list for course
- Conference paper research
- Collaborative project papers
- Personal research interests

**Collection Properties:**
```sql
collections:
  - id (UUID)
  - user_id
  - name (unique per user)
  - description
  - color (hex code for visual distinction)
  - created_at
  - updated_at
```

**Creating Paper Collections:**
1. Navigate to "My Workspace" or "Collections"
2. Click "New Collection"
3. Enter collection name (required)
4. Add description (optional)
5. Choose color (optional, defaults to gray)
6. Click "Create"

**Collection Features:**
- Custom names and descriptions
- Color coding for visual organization
- Paper count display
- Quick add from paper list
- Drag-and-drop organization (UI feature)
- Sort and filter papers within collection

**Adding Papers to Collections:**

**Method 1 - From Paper Detail:**
1. Open paper detail page
2. Click "Add to Collection" button
3. Select one or more collections
4. Click "Add"

**Method 2 - From Library:**
1. Select papers in library view
2. Click "Add to Collection" (bulk action)
3. Choose collection
4. Confirm

**Method 3 - From Collection Page:**
1. Open collection
2. Click "Add Papers"
3. Search and select papers
4. Add to collection

**Viewing Collection Papers:**
- Navigate to `/collections/:collectionId/papers`
- See all papers in collection
- Same features as main library
- Filter and search within collection
- View collection statistics

**Collection Relationships:**
```sql
paper_collections:
  - paper_id (FK to papers)
  - collection_id (FK to collections)
  - added_at (timestamp)
```

**Multi-Collection Support:**
- Papers can belong to multiple collections
- No duplication of paper data
- Many-to-many relationship
- Easy to reorganize

### Chat Collections

**Purpose:**
Group related conversations by topic, project, or context.

**Use Cases:**
- All chats about specific research topic
- Project-related discussions
- Course Q&A conversations
- Methodological discussions
- Brainstorming sessions

**Collection Properties:**
```sql
chat_collections:
  - id (UUID)
  - user_id
  - name (unique per user)
  - description
  - color
  - created_at
  - updated_at
```

**Creating Chat Collections:**
Same process as paper collections:
1. Go to "Chats" or "Collections"
2. Click "New Chat Collection"
3. Fill in name, description, color
4. Save

**Adding Chats to Collections:**

**Method 1 - From Chat:**
1. Open chat
2. Click "Add to Collection" in menu
3. Select collection(s)
4. Confirm

**Method 2 - From Chats Page:**
1. Select multiple chats
2. Bulk action "Add to Collection"
3. Choose collection
4. Apply

**Collection Relationships:**
```sql
chat_collection_relationships:
  - chat_id (FK to chats)
  - collection_id (FK to chat_collections)
  - added_at (timestamp)
```

### Collection Limits by Tier

**Paper Collections:**
| Tier | Max Collections |
|------|-----------------|
| Free | 2 |
| Pro | 20 |
| Nova | 20 |
| Unlimited | ∞ |

**Chat Collections:**
| Tier | Max Collections |
|------|-----------------|
| Free | 2 |
| Pro | 20 |
| Nova | 20 |
| Unlimited | ∞ |

**Limit Enforcement:**
- Clear warning when approaching limit
- Error message when limit reached
- Upgrade prompt displayed
- Suggestion to merge collections

### Collection Management

**Edit Collection:**
- Update name
- Change description
- Modify color
- View statistics

**Delete Collection:**
- Removes collection only
- Papers/chats remain in library
- Confirmation required
- Cannot be undone

**Collection Statistics:**
- Total papers/chats in collection
- Date created
- Last updated
- Most recent additions
- Usage analytics (admin)

### Collection Sharing (Future Feature)

**Planned Features:**
- Share collection with others
- Collaborative collections
- Public/private visibility
- Permission levels (view, edit)
- Collection templates

---

## PDF Viewer & Annotations (Focus)

### Overview

Freiya's Focus mode provides a powerful PDF viewing and annotation experience, allowing researchers to read papers in-depth while taking notes, highlighting key passages, and creating structured annotations.

### Accessing PDF Viewer

**Opening PDFs:**
1. Navigate to paper detail page
2. Click "View PDF" or "Focus" button
3. PDF opens in dedicated viewer
4. Annotations panel appears on right

**PDF Sources:**
- Open access PDFs fetched automatically
- User-uploaded PDFs
- PDFs from arXiv (auto-converted)
- Direct PDF URLs

**Focus Mode Features:**
- Full-screen PDF viewing
- Multi-page navigation
- Zoom controls
- Page thumbnails
- Search within PDF
- Print functionality

### Highlighting System

**Highlight Colors:**
Freiya provides a color-coded highlighting system:

| Color | Common Use | Hex Code |
|-------|------------|----------|
| Yellow | Key findings | #FFEB3B |
| Green | Methodology | #4CAF50 |
| Blue | Important quotes | #2196F3 |
| Red | Critical points | #F44336 |
| Purple | Questions/Todo | #9C27B0 |
| Orange | Examples | #FF9800 |

**Creating Highlights:**
1. Select text in PDF
2. Highlight toolbar appears
3. Choose color
4. Add optional comment
5. Add optional emoji reaction
6. Save highlight

**Highlight Properties:**
```sql
paper_highlights:
  - id (UUID)
  - user_id
  - paper_id
  - document_url
  - highlight_id (unique per highlight)
  - content (JSONB - highlighted text and position)
  - position (JSONB - PDF coordinates)
  - comment_text
  - comment_emoji
  - color (hex code)
  - category (optional categorization)
  - created_at
  - updated_at
```

### Highlight Categories

**Predefined Categories:**
- Methodology
- Results
- Discussion
- Introduction
- Limitations
- Future Work
- Key Concept
- Definition
- Citation
- Custom

**Category Features:**
- Filter highlights by category
- Color-category mapping
- Quick category assignment
- Category statistics

### Annotation Features

**Highlight Toolbar:**
Appears when text is selected:
- Color selection (6 preset colors)
- Add comment button
- Emoji picker
- Category dropdown
- Delete highlight

**Highlight Context Menu:**
Right-click on existing highlight:
- Edit comment
- Change color
- Change category
- Add emoji
- Copy text
- Delete highlight

**Highlight Sidebar:**
Right panel showing all annotations:
- Chronological list of highlights
- Filter by color
- Filter by category
- Search annotations
- Jump to highlight in PDF
- Export highlights

**Highlight Details:**
Each annotation shows:
- Highlighted text (truncated)
- Full comment
- Emoji reaction
- Color indicator
- Page number
- Timestamp
- Edit/delete buttons

### Comments & Notes

**Adding Comments:**
- Comment on any highlight
- Rich text support
- Markdown formatting
- @mentions (future feature)
- Linked notes

**Comment Features:**
- Edit anytime
- Delete comments
- Search comments
- Export with highlights
- Timestamp tracking

**Emoji Reactions:**
- Quick emotional tagging
- Multiple emojis per highlight
- Common reactions:
  - 💡 (insight)
  - ❓ (question)
  - ⭐ (important)
  - 🔍 (investigate)
  - ✅ (understood)
  - 🚨 (critical)

### Navigation & Controls

**PDF Controls:**
- Previous/Next page
- Jump to page number
- Zoom in/out (25% to 400%)
- Fit to width/height
- Full-screen mode
- Rotate pages

**Keyboard Shortcuts:**
- Arrow keys: Navigate pages
- +/- : Zoom
- Ctrl+F: Search in PDF
- Esc: Exit full-screen
- H: Toggle highlights
- N: New note

**Page Thumbnails:**
- Sidebar with page previews
- Quick navigation
- Visual page overview
- Highlight indicators on pages

### Highlight Management

**Bulk Operations:**
- Select multiple highlights
- Change category
- Delete selected
- Export selected
- Change color (batch)

**Export Options:**
- Export all highlights as markdown
- Export to CSV
- Export with comments
- Export by category
- Copy to clipboard

**Export Format Example:**
```markdown
# Highlights from "Paper Title"

## Page 3 - Yellow Highlight
> Highlighted text goes here...

**Comment:** This is my comment about the highlight
**Category:** Methodology
**Date:** 2025-01-15

---
```

### Focus Sessions

**Session Tracking:**
```sql
focus_sessions:
  - id (UUID)
  - user_id
  - paper_id
  - title (default: "Focus Session")
  - last_accessed_at
  - created_at
  - updated_at
```

**Session Features:**
- Auto-save session state
- Resume where you left off
- Track reading progress
- Session history
- Multiple sessions per paper

**Focus Messages:**
In Focus mode, you can ask questions about the paper:

```sql
focus_messages:
  - id
  - session_id
  - paper_id
  - role (user/assistant/system)
  - content
  - chunks (JSONB - relevant paper sections)
  - source (which part of paper)
  - model_used
  - status (processing/complete/error)
  - timestamp
```

**AI-Powered Q&A:**
- Ask questions about the paper
- AI references relevant sections
- Highlights cited passages
- Context-aware responses
- Vector search integration

### Vector Search Integration

**Focus Papers in Vector Store:**
```sql
focus_papers:
  - id
  - paper_id (unique)
  - title
  - authors
  - abstract
  - url
  - publication
  - year
  - citations
  - is_in_vectorstore (boolean)
  - vectorstore_chunks_count
  - last_indexed_at
  - created_at
  - updated_at
```

**Indexing Process:**
1. PDF text extracted
2. Text chunked into sections
3. Embeddings generated (HuggingFace/FastEmbed)
4. Stored in Qdrant vector database
5. Linked to paper_id
6. Available for semantic search

**Semantic Search:**
- Ask natural language questions
- Find relevant passages
- Cross-reference sections
- Compare with other papers
- Discover connections

### Highlight Pro Features

**Advanced Annotation Tools:**
- Drawing tools (shapes, arrows)
- Sticky notes (floating comments)
- Bookmarks
- Outline/Table of contents
- Cross-reference linking
- Collaborative annotations (future)

**Preview for Free Users:**
Shows Pro features with upgrade prompt:
- Grayed out advanced tools
- "Upgrade to Pro" overlays
- Feature descriptions
- Trial period (potential)

---

## Institution Search

### Overview

The Institution Search feature allows researchers to discover and track academic institutions, explore their research output, and identify collaboration opportunities.

### Finding Institutions

**Search Methods:**
1. **Direct Search** - Search by institution name
2. **Paper Affiliations** - Click institution from paper authors
3. **Browse** - Explore curated institution lists
4. **Location-based** - Filter by country or region

**Search Page:**
Located at `/institutions`, provides:
- Search bar with autocomplete
- Filters (country, type, size)
- Results with key metrics
- Map view (future feature)

### Institution Profiles

**Institution Page:**
Located at `/institution/:institutionName`, displays:

**Header Section:**
- Institution name and logo
- Location (city, country)
- Type (University, Research Institute, etc.)
- Official website link
- Social media links

**Key Metrics:**
- Total publications
- Total citations
- H-index
- i10-index
- Active researchers
- Research areas

**Content Sections:**

1. **Overview Tab:**
   - Mission and description
   - Key research areas
   - Notable achievements
   - Rankings and ratings

2. **Publications Tab:**
   - Recent papers from institution
   - Filter by year, citations
   - Search within publications
   - Add to your library

3. **Researchers Tab:**
   - Faculty and researchers
   - Publication counts
   - h-index per researcher
   - Contact information

4. **Collaborations Tab:**
   - Partner institutions
   - Collaboration frequency
   - Joint publications
   - Research networks

5. **Statistics Tab:**
   - Publication trends over time
   - Citation trends
   - Top research areas
   - Funding information

### Data Sources

**Primary Source: OpenAlex**
- Comprehensive institution database
- Regular updates
- Open access data
- Global coverage

**Fallback Sources:**
- Semantic Scholar
- CrossRef metadata
- Manual curation
- User contributions

**Data Refresh:**
- Automatic updates monthly
- Manual refresh option
- Real-time citation counts
- Historical data preserved

### Tracking Institutions

**Follow Institutions:**
- Save institutions to your list
- Get updates on new publications
- Track ranking changes
- Collaboration alerts

**Institution Collections:**
- Group related institutions
- Compare metrics
- Benchmark performance
- Export reports

### Institution Search Features

**Advanced Filters:**
- Country/Region
- Institution type
- Size (student count)
- Research areas
- Ranking tier
- Publication volume

**Sorting Options:**
- Alphabetical
- Citation count
- Publication count
- H-index
- Established date
- Relevance

**Search Results:**
Each result shows:
- Institution name
- Location
- Publication count
- Citation count
- h-index
- Quick actions (View, Follow, Compare)

### Collaboration Discovery

**Find Collaborators:**
- Institutions with similar research
- Geographic proximity
- Complementary strengths
- Active in your field

**Collaboration Metrics:**
- Joint publication count
- Co-authorship networks
- Shared research areas
- Funding partnerships

---

## Subscription & Tiers

### Overview

Freiya offers flexible subscription tiers to accommodate researchers at different stages and with varying needs. All tiers include core features, with higher tiers providing increased limits and advanced capabilities.

### Subscription Tiers

#### Free Tier

**Price:** $0/month

**Features:**
- 5 papers in library
- 5 papers per month limit
- 2 paper collections
- 2 chat collections
- Basic AI models
- Standard usage limits
- Community support
- Email support

**Best For:**
- Students starting research
- Casual users
- Trying out the platform
- Light research needs

**Limitations:**
- Limited paper storage
- Basic model access only
- Fewer collections
- Standard support

#### Pro Tier

**Price:** (To be determined)

**Features:**
- 500 papers in library
- 500 papers per month limit
- 20 paper collections
- 20 chat collections
- Access to advanced AI models
- Increased usage limits
- Priority support
- PDF upload up to 50MB
- Advanced highlighting tools
- Export features
- Usage analytics

**Best For:**
- Graduate students
- Active researchers
- Professional academics
- Regular platform users

**Benefits Over Free:**
- 100x more papers
- 10x more collections
- Better AI models
- Faster support
- Advanced features

#### Nova Tier

**Price:** (To be determined)

**Features:**
- 500 papers in library
- 500 papers per month limit
- 20 paper collections
- 20 chat collections
- Access to specialized AI models
- Premium usage limits
- Priority support
- Advanced analytics
- API access (future)
- Custom integrations

**Best For:**
- Researchers with specialized needs
- Domain experts
- Large research projects
- Specific model requirements

**Unique Features:**
- Specialized AI models
- Custom model fine-tuning (future)
- Advanced integrations
- Premium support tier

#### Unlimited Tier

**Price:** (To be determined)

**Features:**
- Unlimited papers in library
- Unlimited papers per month
- Unlimited paper collections
- Unlimited chat collections
- Access to all AI models
- Unlimited usage
- 24/7 premium support
- All advanced features
- Custom features
- White-label options (enterprise)
- Dedicated account manager
- SLA guarantees

**Best For:**
- Research institutions
- Large research teams
- Enterprise users
- Heavy platform users

**Enterprise Features:**
- No limits on any feature
- Custom contracts
- Bulk licensing
- Team management
- Advanced security
- Dedicated infrastructure
- Custom integrations

### Feature Comparison Table

| Feature | Free | Pro | Nova | Unlimited |
|---------|------|-----|------|-----------|
| Papers in Library | 5 | 500 | 500 | ∞ |
| Papers/Month | 5 | 500 | 500 | ∞ |
| Paper Collections | 2 | 20 | 20 | ∞ |
| Chat Collections | 2 | 20 | 20 | ∞ |
| AI Models | Basic | Advanced | Specialized | All |
| PDF Upload Size | 10MB | 50MB | 100MB | 500MB |
| Usage Limits | Standard | High | Premium | Unlimited |
| Support | Email | Priority | Priority | 24/7 Premium |
| Highlights | Basic | Advanced | Advanced | Advanced |
| Export | Limited | Full | Full | Full |
| API Access | ❌ | ❌ | Future | ✅ |
| Analytics | Basic | Advanced | Advanced | Custom |
| Collaboration | ❌ | Basic | Advanced | Enterprise |

### Tier Limits Configuration

**Technical Implementation:**
```javascript
const TIER_LIMITS = {
  Free: {
    papers: { max: 5, perMonth: 5 },
    collections: { max: 2 },
    chatCollections: { max: 2 }
  },
  Pro: {
    papers: { max: 500, perMonth: 500 },
    collections: { max: 20 },
    chatCollections: { max: 20 }
  },
  Nova: {
    papers: { max: 500, perMonth: 500 },
    collections: { max: 20 },
    chatCollections: { max: 20 }
  },
  Unlimited: {
    papers: { max: -1, perMonth: -1 },
    collections: { max: -1 },
    chatCollections: { max: -1 }
  }
};
```

### Payment & Billing

**Payment Provider:**
- Stripe for payment processing
- Secure PCI-compliant transactions
- Support for credit cards, debit cards
- International payment support
- Automatic billing

**Billing Cycle:**
- Monthly subscriptions
- Annual subscriptions (discount available)
- Automatic renewal
- Cancel anytime
- Prorated upgrades/downgrades

**Payment Flow:**
1. Select desired tier
2. Click "Upgrade" button
3. Redirected to Stripe checkout
4. Enter payment information
5. Confirm subscription
6. Redirected to success page
7. Subscription activated immediately

**Stripe Integration:**
```javascript
// User record includes:
- stripe_customer_id
- stripe_subscription_id
- subscription_tier
- subscription_status (active/inactive/cancelled)
- subscription_start_date
- subscription_current_period_end
```

**Payment Status Pages:**
- `/payment-success` - Successful payment confirmation
- `/payment-canceled` - Cancelled payment page

### Upgrading & Downgrading

**Upgrade Process:**
1. Navigate to Settings > Subscription
2. Click "Upgrade" on desired tier
3. Complete payment
4. Limits increased immediately
5. Confirmation email sent

**Downgrade Process:**
1. Navigate to Settings > Subscription
2. Click "Change Plan"
3. Select lower tier
4. Confirm downgrade
5. Takes effect at end of billing period
6. Keeps data within new limits

**Downgrade Considerations:**
- Papers exceeding limit remain accessible (read-only)
- Must reduce to new limits before adding more
- Collections may need consolidation
- No data loss
- Warning before confirming

### Subscription Management

**Subscription Settings:**
- View current plan
- Usage statistics
- Billing history
- Payment method
- Cancel subscription
- Update billing info

**Cancel Subscription:**
- Instant cancellation or end of period
- No refunds for partial periods
- Access maintained until period end
- Data retained for 30 days
- Can resubscribe anytime

**Failed Payments:**
- Email notification sent
- Retry attempts (3x)
- Grace period (7 days)
- Downgrade to Free if not resolved
- Data preserved

### Override Subscription Status

**Admin Feature:**
```sql
users:
  - override_sub_status (boolean)
```

**Purpose:**
- Testing and development
- Special user privileges
- Grandfathered plans
- Staff accounts
- Promotional access

**When Enabled:**
- Skips Stripe subscription checks
- Bypasses tier limits (optional)
- Maintains specified tier
- No billing required

---

## Settings & Preferences

### Overview

Freiya provides comprehensive settings to customize your experience, manage your account, and control your preferences.

### Account Settings

**Profile Information:**
- Display name
- Email address (verified)
- Profile picture (future)
- Bio/description (future)
- Academic affiliation
- ORCID integration (future)

**Email Settings:**
- Change email address
- Verify new email
- Email preferences
- Notification settings

**Password Management:**
- Change password
- Password requirements enforced
- Old password verification required
- Session invalidation on change

**Password Reset Flow:**
1. Click "Forgot Password"
2. Enter email address
3. Receive reset token via email
4. Click link in email
5. Enter new password
6. Password updated
7. Redirected to login

**Reset Token System:**
```sql
users:
  - password_reset_token (hashed)
  - password_reset_expires (timestamp)
```

**Security:**
- Tokens expire after 1 hour
- One-time use only
- Secure token generation
- Encrypted storage

### Display Preferences

#### Dark Mode

**Toggle Dark Mode:**
- System preference detection
- Manual toggle
- Persisted in localStorage
- Instant theme switching
- Affects entire application

**Dark Mode Features:**
- Optimized color schemes
- Reduced eye strain
- Battery saving (OLED screens)
- Code highlighting adapted
- Image brightness adjusted

**Implementation:**
```javascript
const [darkMode, setDarkMode] = useState(
  localStorage.getItem('darkMode') ||
  window.matchMedia('(prefers-color-scheme: dark)').matches
);
```

**Theme Classes:**
- Tailwind CSS dark mode
- `dark:` prefix for dark styles
- Automatic contrast adjustment
- Accessible color combinations

**Floating Dark Mode Toggle:**
- Fixed button bottom-right
- Slides in on hover
- Sun/moon icon
- Smooth animations (Framer Motion)
- Always accessible

#### Language Settings

**Supported Languages:**
- English (EN)
- Spanish (ES)

**Language Selection:**
- Dropdown in header
- Auto-detection from browser
- Stored in cookies
- Affects UI text
- Affects date/time formatting

**Implementation:**
```javascript
const [language, setLanguage] = useState(() => {
  const saved = Cookies.get('appLanguage');
  if (saved && saved !== 'auto') return saved;

  const browserLang = navigator.language;
  return browserLang.startsWith('es') ? 'ES' : 'EN';
});
```

**Translation Coverage:**
- UI elements
- Error messages
- Notifications
- Email templates
- Help documentation

### Notification Preferences

**Email Notifications:**
- Account security alerts
- Subscription updates
- Payment confirmations
- Usage limit warnings
- Weekly digest (optional)
- Monthly reports (optional)

**In-App Notifications:**
- Real-time toast notifications
- Error alerts
- Success confirmations
- Info messages
- Warning prompts

**Notification Settings:**
- Enable/disable by category
- Frequency preferences
- Digest options
- Quiet hours (future)

### Privacy Settings

**Data Privacy:**
- Download your data
- Delete account
- Export history
- Privacy policy link
- Terms of service link

**Account Deletion:**
- Permanent action warning
- Confirmation required
- Data deletion within 30 days
- Subscription cancelled
- Can create new account later

**Data Export:**
- Export all papers
- Export all chats
- Export highlights
- Export collections
- JSON or CSV format

### Session Management

**Active Sessions:**
```sql
users:
  - session_token
  - session_expires_at
```

**Session Features:**
- JWT-based authentication
- Auto-renewal on activity
- Secure token storage
- Logout on all devices
- Session timeout (24 hours idle)

**Logout Options:**
- Current device only
- All devices
- Clear cookies
- Clear localStorage
- Redirect to login

### API Keys (Future)

**For Developers:**
- Generate API keys
- Key rotation
- Rate limiting
- Usage monitoring
- Revoke keys

**API Key Management:**
- Create new key
- Name and description
- Scope selection
- Expiration date
- View usage stats
- Delete key

### Keyboard Shortcuts

**Customization:**
- View all shortcuts
- Customize bindings
- Reset to defaults
- Export/import settings
- Conflict detection

**Shortcut Categories:**
- Navigation
- Chat actions
- Paper management
- PDF viewer
- Search

---

## Admin Tools

### Overview

Admin Tools provide platform administrators with powerful capabilities to monitor, manage, and maintain the Freiya platform. Access is restricted to users with admin privileges.

### Accessing Admin Tools

**Admin Route:**
- Protected route at `/internal-tools`
- Requires authentication
- Requires admin role
- Protected by `ProtectedAdminRoute` component

**Authentication Check:**
```javascript
<ProtectedAdminRoute>
  <AdminLayout />
</ProtectedAdminRoute>
```

**Admin Role Verification:**
- Checked server-side
- JWT token validation
- Admin flag in user record
- Route middleware protection

### Admin Dashboard

**Location:** `/internal-tools`

**Dashboard Overview:**
- Total users count
- Active subscriptions
- Revenue metrics
- Usage statistics
- System health indicators
- Recent activity feed

**Key Metrics Displayed:**
- User growth (daily/weekly/monthly)
- Subscription distribution
- Model usage by type
- Paper library statistics
- Error rates
- API performance

**Visual Analytics:**
- Line charts (trends)
- Bar charts (comparisons)
- Pie charts (distributions)
- Tables (detailed data)
- Real-time updates

### Views Panel

**Location:** `/internal-tools/views`

**Available Views:**

1. **User Management View:**
   - List all users
   - Search by email/name
   - Filter by subscription tier
   - User details (join date, activity, subscription)
   - Quick actions (view user, suspend, delete)
   - Export user list

2. **Subscription View:**
   - Active subscriptions
   - Subscription status
   - Revenue per tier
   - Churn rate
   - Failed payments
   - Upgrade/downgrade trends

3. **Usage Analytics View:**
   - Model usage by tier
   - Message counts per model
   - Paper additions per tier
   - Collection usage
   - PDF uploads

4. **Content View:**
   - Total papers in system
   - Most saved papers
   - Popular research areas
   - Citation distribution
   - Institution popularity
   - Trending topics

5. **Performance View:**
   - API response times
   - Database query performance
   - Vector search latency
   - Error rates by endpoint
   - Server resource usage
   - Uptime statistics

**View Customization:**
- Filter by date range
- Export to CSV/Excel
- Scheduled reports
- Custom columns
- Saved filters

### Audit Logs

**Location:** `/internal-tools/audit-logs` (Coming Soon)

**Logged Events:**
- User authentication (login/logout)
- Subscription changes
- Payment transactions
- Admin actions
- Data exports
- Account deletions
- API key creation/deletion
- Configuration changes

**Log Details:**
- Timestamp
- User ID
- Action type
- IP address
- User agent
- Before/after state
- Success/failure status
- Error messages (if any)

**Log Features:**
- Search by user/action/date
- Filter by event type
- Export logs
- Retention policy
- Compliance reports

### System Health

**Location:** `/internal-tools/system` (Coming Soon)

**Monitored Systems:**

1. **Database Health:**
   - Connection pool status
   - Query performance
   - Storage usage
   - Backup status
   - Replication lag

2. **Vector Store Health:**
   - Qdrant cluster status
   - Index count
   - Query latency
   - Memory usage
   - Failed operations

3. **AI Model Status:**
   - Model availability
   - Response times
   - Error rates
   - Rate limit status
   - Token usage

4. **External Services:**
   - Stripe API status
   - Semantic Scholar API
   - Email service status
   - Storage service status
   - CDN performance

5. **Server Resources:**
   - CPU usage
   - Memory usage
   - Disk space
   - Network throughput
   - Active connections

**Alerts & Monitoring:**
- Real-time status indicators
- Alert thresholds
- Email notifications
- Incident response
- Auto-scaling triggers

### User Management

**User Actions:**
- View user profile
- Check subscription status
- Override subscription limits
- Reset password
- Verify email manually
- Suspend account
- Delete account
- View usage history
- Grant admin privileges

**Bulk Actions:**
- Export user list
- Send announcements
- Apply tier changes
- Extend trial periods
- Issue refunds

### Configuration Management

**Platform Settings:**
- Feature flags
- Model availability
- Usage limits
- Pricing tiers
- Email templates
- Notification settings
- Maintenance mode

**Feature Flags:**
- Enable/disable features
- A/B testing
- Gradual rollouts
- Emergency shutoffs
- Beta feature access

### Database Administration

**Admin Routes:**
```javascript
const adminRoutes = require('./routes/adminRoutes');
app.use('/api/admin', conditionalAuth, adminRoutes);
```

**Database Operations:**
- Run migrations
- View table schemas
- Execute queries (with caution)
- Database backups
- Restore from backup
- Cleanup operations

**Safety Features:**
- Transaction support
- Rollback capability
- Confirmation prompts
- Audit logging
- Read-only mode option

### Analytics & Reporting

**Custom Reports:**
- User growth reports
- Revenue reports
- Usage reports
- Performance reports
- Error reports
- Security reports

**Report Features:**
- Schedule generation
- Email delivery
- PDF/Excel export
- Interactive dashboards
- Customizable metrics
- Comparison periods

**Report Types:**
- Daily summaries
- Weekly digests
- Monthly reviews
- Quarterly analysis
- Annual reports
- Ad-hoc custom reports

### Security & Compliance

**Security Monitoring:**
- Failed login attempts
- Unusual activity patterns
- API abuse detection
- Data breach alerts
- Vulnerability scans

**Compliance Tools:**
- GDPR data exports
- Right to deletion
- Data retention policies
- Privacy audit logs
- Terms acceptance tracking

---

## Keyboard Shortcuts

### Overview

Freiya provides keyboard shortcuts to enhance productivity and streamline common workflows. Shortcuts are available throughout the application with context-specific bindings.

### Global Shortcuts

**Navigation:**
- `Ctrl/Cmd + K` - Quick search (papers, chats, institutions)
- `Ctrl/Cmd + N` - New chat
- `Ctrl/Cmd + P` - Add new paper
- `Ctrl/Cmd + ,` - Open settings
- `Ctrl/Cmd + /` - Show keyboard shortcuts help

**Display:**
- `Ctrl/Cmd + D` - Toggle dark mode
- `Ctrl/Cmd + B` - Toggle sidebar
- `Esc` - Close modal/dialog

### Chat Shortcuts

**Chat Interface:**
- `Enter` - Send message (unless Shift held)
- `Shift + Enter` - New line in message
- `Ctrl/Cmd + ↑` - Edit last message
- `Ctrl/Cmd + R` - Regenerate response
- `Ctrl/Cmd + L` - Clear chat
- `Ctrl/Cmd + E` - Export chat

**Chat Navigation:**
- `↑/↓` - Navigate chat history
- `Ctrl/Cmd + [` - Previous chat
- `Ctrl/Cmd + ]` - Next chat
- `Ctrl/Cmd + W` - Close current chat

**Message Actions:**
- `Ctrl/Cmd + C` - Copy message (when hovering)
- `Ctrl/Cmd + Delete` - Delete message
- `Ctrl/Cmd + S` - Save chat

### Paper Library Shortcuts

**Library Navigation:**
- `Ctrl/Cmd + F` - Focus search box
- `Ctrl/Cmd + A` - Select all papers
- `Ctrl/Cmd + Click` - Multi-select
- `Shift + Click` - Range select
- `Delete` - Delete selected papers

**Paper Actions:**
- `Enter` - Open selected paper
- `Ctrl/Cmd + O` - Open paper PDF
- `Ctrl/Cmd + T` - Add tags to selected
- `Ctrl/Cmd + M` - Add to collection

**Sorting & Filtering:**
- `Ctrl/Cmd + 1-5` - Apply preset filters
- `Ctrl/Cmd + Shift + S` - Change sort order
- `Ctrl/Cmd + Shift + F` - Advanced filters

### PDF Viewer Shortcuts (Focus)

**Navigation:**
- `→` or `Space` - Next page
- `←` or `Shift + Space` - Previous page
- `Home` - First page
- `End` - Last page
- `Page Up/Down` - Scroll page

**Zoom & Display:**
- `Ctrl/Cmd + +` - Zoom in
- `Ctrl/Cmd + -` - Zoom out
- `Ctrl/Cmd + 0` - Reset zoom
- `F` or `F11` - Toggle fullscreen
- `Ctrl/Cmd + F` - Search in PDF

**Annotations:**
- `H` - Toggle highlights visibility
- `N` - New note
- `C` - Add comment to selection
- `Delete` - Delete selected highlight
- `Ctrl/Cmd + H` - Highlight with last color

**Sidebar:**
- `Ctrl/Cmd + Shift + H` - Toggle highlights sidebar
- `Ctrl/Cmd + Shift + T` - Toggle thumbnails
- `Ctrl/Cmd + Shift + O` - Toggle outline

### Collection Shortcuts

**Collection Management:**
- `Ctrl/Cmd + Shift + N` - New collection
- `Ctrl/Cmd + E` - Edit collection
- `Delete` - Delete collection (with confirmation)

**Adding to Collections:**
- `Alt/Opt + 1-9` - Quick add to collection (1-9)
- `Ctrl/Cmd + Shift + A` - Add to multiple collections

### Search Shortcuts

**Universal Search:**
- `/` - Focus search anywhere
- `Ctrl/Cmd + K` - Quick command palette
- `Esc` - Clear search
- `Enter` - Go to first result
- `Tab` - Navigate results

**Advanced Search:**
- `Ctrl/Cmd + Shift + F` - Advanced search modal
- `Alt/Opt + A` - Search papers
- `Alt/Opt + C` - Search chats
- `Alt/Opt + I` - Search institutions

### Text Editing Shortcuts

**Rich Text Editor:**
- `Ctrl/Cmd + B` - Bold
- `Ctrl/Cmd + I` - Italic
- `Ctrl/Cmd + U` - Underline
- `Ctrl/Cmd + K` - Insert link
- `Ctrl/Cmd + Z` - Undo
- `Ctrl/Cmd + Shift + Z` - Redo

**Markdown Shortcuts:**
- `Ctrl/Cmd + Shift + C` - Code block
- `Ctrl/Cmd + Shift + L` - Bullet list
- `Ctrl/Cmd + Shift + O` - Numbered list
- `Ctrl/Cmd + Shift + Q` - Blockquote

### Admin Shortcuts

**Admin Panel:**
- `Ctrl/Cmd + Alt + A` - Open admin dashboard
- `Ctrl/Cmd + Alt + U` - User management
- `Ctrl/Cmd + Alt + S` - System health
- `Ctrl/Cmd + Alt + L` - View logs

### Customization

**Keyboard Shortcuts Provider:**
```javascript
import { KeyboardShortcutsProvider } from './contexts/KeyboardShortcutsContext';
```

**Features:**
- Context-aware shortcuts
- Customizable bindings (future)
- Conflict detection
- Help overlay
- Platform detection (Mac vs Windows)

**Shortcut Help Overlay:**
- Press `?` to show all shortcuts
- Grouped by context
- Search shortcuts
- Visual key indicators
- Printable reference

---

## Tips & Best Practices

### Research Workflow Optimization

#### 1. Organize Early, Organize Often

**Best Practices:**
- Create collections before adding papers
- Use consistent naming conventions
- Tag papers immediately upon adding
- Write notes while reading
- Link related papers

**Recommended Organization:**
```
Collections:
├── Thesis Chapter 1
├── Thesis Chapter 2
├── Literature Review - ML
├── Methodology References
├── To Read
└── Key Papers

Tags:
├── methodology
├── results
├── theoretical-foundation
├── future-work
├── critical
└── to-cite
```

#### 2. Effective Paper Management

**Adding Papers:**
- Use DOI when available (most accurate metadata)
- Verify author affiliations
- Add tags immediately
- Write brief summary in notes
- Check for PDF availability

**Reading Workflow:**
1. Add paper to "To Read" collection
2. Skim abstract and conclusions
3. Add initial tags
4. Move to relevant project collection
5. Deep read with highlighting (Focus mode)
6. Write detailed notes
7. Link to related papers
8. Generate citation

#### 3. AI Chat Strategies

**Effective Prompting:**
- Be specific in questions
- Provide context when needed
- Break complex queries into steps
- Reference papers when relevant
- Follow up for clarification

**Examples:**

**❌ Poor Prompt:**
"Tell me about machine learning"

**✅ Good Prompt:**
"Explain the difference between supervised and unsupervised learning in the context of medical image analysis, with examples from recent papers"

**✅ Great Prompt:**
"I'm reading [Paper Title]. Can you explain how their novel attention mechanism (Section 3.2) differs from standard self-attention, and why they claim it improves performance on long sequences?"

**Chat Organization:**
- Use descriptive chat titles
- Pin important conversations
- Create topic-specific chat collections
- Link chats to relevant papers
- Export valuable discussions

#### 4. Highlighting & Annotation

**Color Coding System:**
- **Yellow** - Key findings and main results
- **Green** - Methodology and approach
- **Blue** - Important quotes for citation
- **Red** - Critical points and limitations
- **Purple** - Questions and future work
- **Orange** - Examples and case studies

**Effective Annotations:**
- Add context to highlights
- Use emojis for quick categorization
- Write questions as comments
- Link to related concepts
- Reference other papers

**Example Workflow:**
1. First read: Yellow highlights on key findings
2. Second read: Green on methodology
3. Third read: Blue on quotable passages
4. Writing phase: Export highlights as outline

#### 5. Collection Strategies

**Collection Types:**

**Project-Based:**
- Thesis Chapter 1
- Grant Proposal - NSF
- Conference Paper - ICML 2025

**Topic-Based:**
- Deep Learning Architectures
- Biomedical Applications
- Ethical Considerations

**Status-Based:**
- To Read
- Currently Reading
- Read & Summarized
- Key References

**Purpose-Based:**
- Methodology Papers
- Background & Context
- Related Work
- Future Directions

#### 6. Search Optimization

**Effective Searching:**
- Use specific keywords
- Combine multiple terms
- Filter by year for recent work
- Sort by citation count for influential papers
- Use author names for specific researchers

**Search Tips:**
- Search DOI for exact paper
- Use quotes for exact phrases
- Use AND/OR for boolean searches
- Filter after searching
- Save frequent searches (future feature)

#### 7. Subscription Tier Selection

**Choosing the Right Tier:**

**Free Tier - Best For:**
- Trying out the platform
- Very light research needs
- Students with limited papers
- Side projects

**Pro Tier - Best For:**
- Active graduate students
- Researchers with ongoing projects
- Literature review projects
- Multiple active research areas

**Unlimited Tier - Best For:**
- Research faculty
- Large research teams
- Extensive paper libraries
- Professional researchers

**Upgrade Triggers:**
- Hitting paper limit frequently
- Need for more collections
- Requiring advanced AI models
- Team collaboration needs

#### 8. Productivity Habits

**Daily Workflow:**
1. **Morning:** Review new papers in field (set up alerts)
2. **Reading Session:** Deep read 1-2 papers with highlights
3. **Writing Session:** Use highlights to draft sections
4. **AI Chat:** Clarify concepts, explore ideas
5. **Organization:** Tag, categorize, update notes

**Weekly Habits:**
- Review all new papers added
- Clean up tags and collections
- Export important highlights
- Backup citations
- Plan next week's reading

**Monthly Review:**
- Evaluate subscription usage
- Archive completed projects
- Reorganize collections
- Update reading priorities
- Review AI chat history for insights

#### 9. Collaboration (Current & Future)

**Sharing Best Practices:**
- Share important chats with colleagues
- Export collections as citation lists
- Create standardized tags for teams
- Document search strategies
- Share highlight templates

**Future Collaboration:**
- Shared collections
- Collaborative annotations
- Team workspaces
- Comment threads
- Real-time editing

#### 10. Data Management

**Backup Strategy:**
- Regular exports of papers
- Save important chat transcripts
- Download PDF backups
- Export highlights periodically
- Keep local copies of citations

**Export Formats:**
- BibTeX for LaTeX users
- RIS for EndNote/Mendeley
- CSV for Excel analysis
- Markdown for notes
- PDF for archival

#### 11. Ethical Research Practices

**Citation Integrity:**
- Always cite sources properly
- Use generated citations as starting point
- Verify citation format
- Check original paper
- Give credit appropriately

**AI Usage Ethics:**
- Use AI as assistant, not replacement
- Verify AI-provided information
- Cite original sources, not AI
- Understand concepts fully
- Credit human collaborators

#### 12. Performance Optimization

**Speed Tips:**
- Use keyboard shortcuts
- Pin frequently used chats
- Create focused collections
- Limit search scope
- Close unused chats

**Storage Management:**
- Delete duplicate papers
- Remove old, unused collections
- Archive completed projects
- Clean up test data
- Monitor tier limits

---

## Conclusion

Freiya is a comprehensive research assistant platform designed to streamline academic workflows. By combining powerful AI capabilities with robust paper management, annotation tools, and organizational features, Freiya helps researchers focus on what matters most: their research.

### Key Takeaways

1. **AI-Powered:** Multiple AI models for diverse research needs
2. **Organized:** Collections, tags, and powerful search
3. **Annotated:** Deep reading with highlights and notes
4. **Flexible:** Tiered pricing for different needs
5. **Integrated:** Seamless workflow from discovery to citation

### Getting Help

- **Documentation:** This guide and online help
- **Support:** Email support for all tiers
- **Community:** (Future) Discord community
- **Feature Requests:** Submit via feedback form
- **Bug Reports:** GitHub issues or email

### Roadmap (Future Features)

- Collaborative workspaces
- API access for integrations
- Mobile applications
- Browser extensions
- Reference manager sync
- Advanced analytics
- Custom AI model training
- Team management
- Institutional plans

---

**Document Version:** 1.0
**Last Updated:** January 2025
**Platform Version:** Current
**For Mintlify Conversion:** Yes

---

**End of Freiya Platform Documentation**
