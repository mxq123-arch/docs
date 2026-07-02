# Source: https://github.com/mintlify/docs/blob/main/.vale/README.md

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# README.md

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/.vale/README.md)

History

42 lines (32 loc) · 1.4 KB

 main

/

# README.md

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

42 lines (32 loc) · 1.4 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/.vale/README.md)

Copy raw file

Download raw file

Outline

Edit and raw actions

# Vale Configuration for Mintlify Docs

This directory contains the Vale linting configuration for Mintlify documentation.

## Philosophy

Start simple and grow incrementally as needs emerge.

## Vale files

- `.vale.ini` - Main configuration file
- `styles/config/vocabularies/Mintlify/` - Mintlify-specific terms
- `styles/Mintlify/` - Style rules derived from the Google developer documentation style and customized for Mintlify

## When to add vocabulary

- **Mintlify terms** - New components, features, platform-specific concepts
- **Frequent false positives** - Any terms that repeatedly trigger errors, but shouldn't

### Discover new vocabulary

Use the included script to find vocabulary candidates:

```shell
# Discover terms from all files
.vale/scripts/discover-vocabulary.sh

# Discover from specific files
.vale/scripts/discover-vocabulary.sh "components/*.mdx"
```

This script:

1. Runs Vale on specified files
2. Extracts spelling error suggestions
3. Saves results to `.vale/vocabulary-candidates.txt`

## When to add new rules

- **Consistent patterns** - The same style issue appears frequently
- **High-value, low-noise** - Rules that catch problems with minimal false positives

### Testing new rules

Before adding a new rule:

1. Test locally: `vale path/to/file.mdx`
2. Run on sample files: `vale components/*.mdx`
3. Check false positive rate
4. Start with `level: suggestion` then promote to `warning` or `error`