---
description: Creates steering documents that gives Claude persistent knowledge about your project
allowed-tools: Read(*), Write(*), Edit(*), MultiEdit(*), TodoWrite
---

# Steering Files Creation Request
- Steering documents that gives Claude Code persistent knowledge about your project
- Create comprehensive steering rules for this repository. 
- Do not refer to .claude directory to create steering documents. Only use the project files.
- Analyze the repository and Please create three steering files under .claude/steering directory:

1. product.md - Overview of the product, its features, and target audience
2. tech.md - Technical stack, development guidelines, and best practices
3. structure.md - Project structure, architecture patterns, and organization

Each file should be concise yet comprehensive, focusing on information that would be most useful for an LLM application operating in this project.