# EderSpark AI Documentation

## Working relationship
- You can push back on ideas - this can lead to better documentation. Cite sources and explain your reasoning when you do so
- ALWAYS ask for clarification rather than making assumptions
- NEVER lie, guess, or make up information
- Prioritize scientific accuracy and cite peer-reviewed sources when possible

## Project context
- **Company**: EderSpark - AI research company in Córdoba, Spain
- **Mission**: Accelerate scientific discovery through advanced AI tools
- **Products**: Freiya Platform (semantic search over 200+ million scientific papers)
- **Format**: MDX files with YAML frontmatter
- **Config**: docs.json for navigation, theme, settings
- **Components**: Mintlify components

## Content strategy
- Document comprehensive AI knowledge from fundamentals to cutting-edge research
- Prioritize accuracy and scientific rigor over completeness
- Make content evergreen when possible - focus on principles over specific implementations
- Search for existing information before adding new content. Avoid duplication unless it is done for a strategic reason
- Check existing patterns for consistency
- Start by making the smallest reasonable changes
- Include both theoretical foundations and practical applications
- Emphasize EderSpark's expertise in scientific AI applications

## Documentation scope
This documentation covers:
1. **AI Fundamentals**: Core concepts, history, mathematical foundations
2. **Large Language Models**: Architecture, training, capabilities, limitations
3. **AI Agents**: Autonomous systems, multi-agent coordination, reasoning
4. **Training & Infrastructure**: Distributed training, optimization, scaling
5. **Alignment & Safety**: AI safety, value alignment, responsible development
6. **Interactions & Applications**: Human-AI interaction, scientific applications

## Frontmatter requirements for pages
- title: Clear, descriptive page title
- description: Concise summary for SEO/navigation

## Writing standards
- Second-person voice ("you") for instructional content
- Third-person for scientific explanations and theory
- Prerequisites at start of procedural content
- Test all code examples before publishing
- Match style and formatting of existing pages
- Include both basic and advanced use cases
- Language tags on all code blocks
- Alt text on all images
- Relative paths for internal links
- Cite scientific sources when making factual claims
- Balance theoretical rigor with practical accessibility

## Technical accuracy
- All mathematical formulations must be correct
- Code examples should be functional and well-commented
- Scientific claims should be backed by peer-reviewed sources
- Acknowledge limitations and current research gaps
- Distinguish between established knowledge and cutting-edge research

## Git workflow
- NEVER use --no-verify when committing
- Ask how to handle uncommitted changes before starting
- Create a new branch when no clear branch exists for changes
- Commit frequently throughout development
- NEVER skip or disable pre-commit hooks

## Do not
- Skip frontmatter on any MDX file
- Use absolute URLs for internal links
- Include untested code examples
- Make assumptions - always ask for clarification
- Oversimplify complex AI concepts to the point of inaccuracy
- Present speculative research as established fact
````
