## Step 2: Agent Mode and an MCP Server for GitHub

Great work! You just connected your first MCP server to GitHub Copilot! 🎉

🚨 The teachers have been busy opening new issues in your repository with bugs and feature requests! Go [take a look](https://github.com/{{full_repo_name}}/issues) - so many good ideas!

We should probably look into them and start researching for other upgrades. Fortunately, with an MCP server for GitHub, triaging these and even doing some research to get ahead should be pretty quick! 🕵️

### 📖 Theory: How MCP Tool Calling Works in Agent Mode

Now that we have the GitHub MCP connected, let's look at how **agent mode** actually uses these external tools.

With every prompt you send, Copilot also includes the catalog (list + schema) of available tools. Copilot can then plan and decide:

- Is any tool needed for this request?
- Which tool(s) best match the intent?
- What arguments (per each tool's input schema) should be passed?

Copilot then executes the chosen tool call(s) and streams results back to the LLM.

![Flowchart diagram illustrating how a user interacts with Copilot Agent Mode](https://github.blog/wp-content/uploads/2025/05/how-it-works.png)

> [!TIP]
> You can also explicitly nudge Copilot to call a specific tool by including `#<tool_name>` in your prompt (e.g `#create_pull_request`, `#codebase`).

From here, Copilot can use a set of GitHub‑aware tools to do more than just read or edit code in your repo. Here are a few things you can ask it to do:

- Discover similar public projects to get inspiration.
- Search issues considering description, comments, and likes.
- Turn the new ideas you like into issues right away so you don’t lose them.
- Retrieve an issue, make changes on a branch, and start a pull request.

Isn't that cool?! Now let's do it! 👩‍🚀

### :keyboard: Activity: Quickly find and save ideas

Let's put the GitHub MCP server to use by researching, comparing, and capturing enhancement ideas!

1. Close any open files inside your codespace. This will help reduce unnecessary context.

1. Ensure the **Copilot Chat** panel is open and **Agent** mode is selected. Verify the MCP server tools are also still available.

1. Ask Copilot to search GitHub for projects similar to this one.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Search for any other repositories for organizing extra curricular activities
   > ```

1. When an MCP tool is required, Copilot may ask for permission. **Verify the request** and modify if necessary, then click **Continue**.

   <img width="250" alt="request permission dialog" src="https://github.com/user-attachments/assets/229473af-c206-47a4-b356-943b9c9bd946" />

1. Ask Copilot to describe one of the projects. Explore until you find something you like.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Please look at the code for the 3rd option and give me a detailed description of the features.
   > ```

1. Use Copilot to compare and generate ideas for enhancements.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Please compare these features to our project. Which would be new?
   > ```

1. Nice! Let's have Copilot create issues to save these ideas.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > I like it. Let's create issues for these in my repository.
   > ```

1. Copilot will ask for permission to create issues on your repository. Click **Continue** for each new issue. Reminder: **verify the request** before running.

   <img width="250" alt="request permission dialog" src="https://github.com/user-attachments/assets/52635294-950a-4168-b71e-498eb769f3af" />

1. Since we are done researching, let's finish this chat session to clear the context. At the top of the **Copilot Chat** panel, click the **New Chat** icon (plus sign).

1. With the new issues created, Mona should already be busy checking your work. Give her a moment and keep watch in the comments. You will see her respond with progress info and the next lesson.

> [!NOTE]
> The Model Context Protocol (MCP) landscape is quickly evolving. Many servers, including the [Official GitHub MCP server](https://github.com/github/github-mcp-server) are in active development and do not have full parity with their stable APIs.
