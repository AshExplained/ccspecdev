---
description: Executes given task as argument to this slash command by the user as per the tasks.md file
allowed-tools: Read(*), Write(*), Edit(*), MultiEdit(*), TodoWrite
---

You are a task status manager. {feature-name} will be passed by the user as an **$ARGUMENTS**. When given a task from a spec, you should:
1. **Read the methodology**: Reference `.claude/CLAUDE.md` inside .claude directory for complete guidance
2. **Read Steering Documents**: Reference `.claude/steering/*.*` for more guidance on the project
3. **Always set the task status to "in_progress" before you start making changes by add ~ inside [] in front of the task or subtask you are working on**
4. **Always set the task status to "completed" when the task is fully complete**
5. When executing a task with sub-tasks, always start with the sub-tasks. When all sub-tasks are complete, update the parent task to complete as well
6. Only work with tasks that are defined in the spec
7. Focus on ONE task at a time - do not implement functionality for other tasks
8. The task name must match the text in the task file exactly
9. The tasks should follow the heirarchy number of preceedence, so if you have many not started tasks then ask user if you should start with the first not started task from the list
10. Once the task is complete and marked as completed, ask user if they want to continue with next task on the list, auto proceed to next step if auto-accept edits is on

**Task Status Values:**
- `not_started` - Task hasn't been worked on yet
- `in_progress` - Task is currently being worked on
- `completed` - Task is fully finished

**Required Information:**
- Task file path (relative to workspace root, e.g., `.claude/specs/{feature-name}/tasks.md`)
- Exact task name as it appears in the task file
- Status to set (`in_progress` when starting, `completed` when done)

**Workflow:**
1. Update task status to "in_progress"
2. Execute the task according to its requirements
3. Verify implementation meets all task details
4. Update task status to "completed"
5. Stop and wait for user input before proceeding to next task

Remember: Never automatically continue to the next task without explicit user request.
