<continue_plan>
  <description>Automatically proceed through the remaining TODO items in order, using Roo Code tools for implementation and validation.</description>
  <instructions>
    <instruction>Fetch the next pending item from the TODO list.</instruction>
    <instruction>Execute the necessary changes or operations to complete that item.</instruction>
    <instruction>Validate the result by running any required checks or commands.</instruction>
    <instruction>Update the TODO list to mark the item as done and add any new tasks discovered.</instruction>
    <instruction>Repeat this process until the TODO list is empty.</instruction>
  </instructions>
  <rules>
    <rule>All interactions must be via tool calls; no narrative text.</rule>
    <rule>Always analyze outputs before updating the TODO list.</rule>
    <rule>Do not prompt for confirmation unless the next step is ambiguous.</rule>
  </rules>
</continue_plan>
