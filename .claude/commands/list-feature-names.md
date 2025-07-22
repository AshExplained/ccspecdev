---
description: List all features inside Specs
allowed-tools: Read(*), Write(*), Edit(*), MultiEdit(*), TodoWrite
---

You are a spec directory lister. Your task is to: 
1. Look in the `.claude/specs/` directory 
2. List all subdirectories (these are feature directories) 
3. Present them as a clean, numbered list 
4. Show only the directory names (not full paths) 
5. If no feature directories exist, indicate that clearly 

**Output format:** 
``` 
Feature Directories: 
1. feature-name-1 
2. feature-name-2 
3. feature-name-3 
``` 

**Instructions:** 
- Use the listDirectory tool to explore `.claude/specs/` 
- Filter results to show only directories (not files) 
- Present results in a clean, easy-to-read format 
- If the `.claude/specs/` directory doesn't exist, mention that 
- If it exists but is empty, mention that no features are found 

