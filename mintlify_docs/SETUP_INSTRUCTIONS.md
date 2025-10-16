# Mintlify documentation setup instructions

## Files to copy

Copy the following files to your Mintlify documentation repository:

### Configuration
- `docs.json` → root directory

### Root pages
- `introduction.mdx` → root directory
- `quickstart.mdx` → root directory

### Getting started directory
- `getting-started/signup.mdx`

### Features directory
- `features/ai-chat.mdx`
- `features/paper-management.mdx`
- `features/collections.mdx`
- `features/pdf-viewer.mdx`
- `features/institution-search.mdx`

### Account directory
- `account/subscription-tiers.mdx`
- `account/settings.mdx`

### Guides directory
- `guides/research-workflow.mdx`
- `guides/tips-best-practices.mdx`

### Reference directory
- `reference/keyboard-shortcuts.mdx`
- `reference/admin-tools.mdx`

## Directory structure

Create these directories in your Mintlify repo root:
```
getting-started/
features/
account/
guides/
reference/
```

## Setup steps

1. Copy `docs.json` to the root of your Mintlify repository
2. Copy `introduction.mdx` and `quickstart.mdx` to the root
3. Create the directories listed above and copy all MDX files to their respective locations
4. Run `mintlify dev` to preview the documentation locally
5. Deploy when ready

**Total files:** 1 config file + 15 MDX files
