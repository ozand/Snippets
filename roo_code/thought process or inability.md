Understood. Let’s break the task into smaller steps:

1. Invoke the `Sequential Thinking` MCP tool to outline the full sub-step plan for this task.
2. For each sub-step, verify which Roo Code tool should be used (e.g., `apply_diff`, `list-files`, `read-file`).
3. Execute and validate one sub-step at a time, using `ask_followup_question` if any input is unclear.
4. After each sub-step, update the TODO list before moving on.

Please start by calling:
<use_mcp_tool server_name="Sequential Thinking">
  <uri>st://break-down-task</uri>
</use_mcp_tool>
