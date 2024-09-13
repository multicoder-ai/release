# Claude 3.5 Sonnet in Copilot Chat

Add **Claude 3.5 Sonnet** and other models to your GitHub Copilot chat.

![](https://multicoder.dev/resources/readme/overview.gif)

Multicoder extends Copilot chat with additional models, available as _chat participants_. Type the **@** symbol and select the model you want to use.

![](https://multicoder.dev/resources/readme/participants.png)

These additional models are not provided by the GitHub Copilot service. To enable them, you need to create an account on the provider's website and generate your own API key.

## Setup

Start your first session with the /config command:

```
@claude /config
```

![](https://multicoder.dev/resources/readme/config.png)

Visit the provider's website, create an account for API use, and generate your own API key. Then, assign your key to the model using the `Set API key` button.

## Features

![](https://multicoder.dev/resources/readme/using.png)

### On-demand Context

This extension allows models to **read files and directories** in your current workspace (except those excluded by .gitignore). You don't always need to manually insert your code into the request context; in many cases, the model will automatically determine which files are required.

**ATTENTION!** Do not use this extension if you don't want your code fragments to be sent to the model provider's server.

Multicoder adds the following context to the initial request:

- A list of files and folders in the project root
- Names of open files in the current workspace
- Name of the file in the active editor
- Selected text in the active editor

### Apply/Undo Changes

To apply code changes to your original files, click the **Apply** button. Click again to revert the changes.

### Diff View

You can open the diff view by clicking on the blue link just above the code block. The diff combines all changes per file in this conversation.

## Feedback

This extension is in early development. Please raise an issue if something doesn't work as expected:

- [https://github.com/multicoder-ai/vscode-release/issues](https://github.com/multicoder-ai/vscode-release/issues)

Questions or suggestions? Visit:

- [https://github.com/multicoder-ai/vscode-release/discussions](https://github.com/multicoder-ai/vscode-release/discussions)

## Download

The extension is available on VSCode Marketplace -

- [Download VS Code extension](https://marketplace.visualstudio.com/items?itemName=multicoder.multicoder)
