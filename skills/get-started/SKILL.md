---
name: get-started
description: Get a user started with Steadybit right after they connect it, or when they ask to set up, try or get started with Steadybit, or what they can do with it. Finds out where they stand (a new trial on sample data, or their own systems) and walks them to a first result.
---

# Get started with Steadybit

1. Call the Steadybit tool `get_started`. It returns where the user stands and `guidance` on what to show them first.
   Follow that guidance; it is kept up to date on the server and takes precedence over anything below.
2. If `get_started` is not available:
   - If the only Steadybit tool is `steadybit_connection_setup`, call it and pass its explanation on.
   - If there are no Steadybit tools at all, the connection is not set up yet. Ask the user to connect Steadybit in
     their assistant's connector or MCP server settings and sign in (in a command-line assistant usually via `/mcp`).
     A new user can create a free trial while signing in.
3. Keep the answer short and end with the example prompts from the result as choices. For anything beyond the first
   steps, the `steadybit` skill covers how to explore, design and run experiments safely.
