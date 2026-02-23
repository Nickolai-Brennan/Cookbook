# Planning a project with GitHub Copilot

Plan your next project by using GitHub Copilot to turn your ideas into issues.

> \[!NOTE]
>
> * This feature is in public preview and subject to change.
> * The responses shown in this article are examples. Copilot Chat responses are non-deterministic, so you may get different responses from the ones shown here.

Manage your project with GitHub Issues using Copilot. In this tutorial, you’ll use Copilot’s agentic issue creation features to turn your product idea into epics, features, and tasks. Epics represent large bodies of work, while features and tasks break the work into smaller, actionable pieces. By the end, you’ll have a structured backlog ready to share with your team.

## Project overview

It’s important to define what you want your product to do. In the planning phase of the software development lifecycle (SDLC), you turn ideas into actionable tasks by breaking down your project into epics, features, and smaller pieces of work. This helps you organize your thoughts, set priorities, and prepare your team for development.

When you use Copilot, you drive this process. Copilot can suggest a structure and fill in details, but the best results come when you have a sense of how you want the work to be organized. Copilot works with your input to help you refine, expand, and document your plan.

In this scenario you’ll plan a new shopping website that will allow users to:

* Browse a product catalog with categories and search
* Add items to a shopping cart
* Complete secure checkouts

Your goal is to use Copilot to quickly turn this vision into a structured project plan, creating epics and detailed issues that capture each part of your site.

## Set up repository

Set up a repository with GitHub Issues enabled. See [Creating a new repository](/en/repositories/creating-and-managing-repositories/creating-a-new-repository).

By default, issues are enabled for new repositories. If you would like to use an existing repository but don’t see the **Issues** tab, follow these steps to enable issues:

1. From the repository, select **Settings**.
2. Under "Features", check the **Issues** box.

## Generate project issues

With the repository set up, you can use Copilot to turn your project vision into a set of actionable issues.

### Start in Copilot in GitHub

1. At the top right of any page on GitHub, click the **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="Copilot icon" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg>** button next to the search bar.

   Copilot Chat is displayed.
2. Using the chat panel, attach the repository for the shopping website. This allows Copilot to access the repository and create issues directly within it.

### Create an epic issue

1. Enter a detailed project description as your prompt. For example:
   `I’m planning to create a shopping website in React and Node.js. The site should allow users to browse products by category, search for items, add products to a cart, and complete checkout. Please help me plan the project by creating issues and breaking it down into epics, features, and tasks.`
2. Submit your prompt. Copilot will generate an issue tree, typically with an epic at the top and sub-issues for each main feature or task

![Screenshot of Copilot Chat. Copilot chat displays a list of issues with an epic at the top and several sub-issues beneath it.](/assets/images/help/copilot/copilot-creates-sub-issues.png)

## Navigate the issue tree

1. Click the epic to view its details in the workbench. Navigate through the workbench to explore the issue tree.

2. Each issue typically includes a title and description. Additional metadata such as labels or assignees, can be edited directly in the workbench.

3. You can expand or collapse sub-issues to focus on specific parts of the project.

   The issue tree provides a clear overview of your project structure, making it easy to navigate between epics, features, and tasks.

4. In this first iteration of the draft, Copilot may generate only high-level issues. You can refine these issues further by breaking them down into smaller tasks or features. Let's refine the issue "Feature: UI Skeleton and Navigation".

   Prompt Copilot with:
   `Can you break down the issue "Feature: UI Skeleton and Navigation" into smaller tasks?`

   Copilot will generate multiple new sub-issues such as:

   * Task: Set up React project structure and initial files
   * Task: Create placeholder pages for main routes
   * Task: Implement site-wide navigation bar component
   * Task: Integrate navigation with routing
   * Task: Add basic responsive layout

5. Repeat this process for the remaining feature issues in the epic.

![Screenshot of the Copilot Chat workbench. The workbench displays an issue tree with an epic at the top and several sub-issues beneath it.](/assets/images/help/copilot/copilot-creates-sub-issues-workbench.png)

### Improve issue descriptions

After you finish generating the issue tree you may notice that Copilot’s issue descriptions may be brief or unclear. To make them actionable, refine each issue as needed.

1. Start with the newly generated issue such as "Task: Create placeholder pages for main routes".

   Prompt Copilot with:
   `Can you improve the description for “Task: Create placeholder pages for main routes”? Please provide a detailed technical summary, list the main routes to be included, outline the steps for implementation, and specify what should be delivered for this task. Please add any relevant code snippets.`

2. Copilot will generate a new version of the draft issue "Task: Create placeholder pages for main routes."

   At the top-left of the issue, click the versioning drop-down and select **Version 2** to review the new changes.

3. Review and decide whether to keep Copilot’s revised version, edit further, or prompt again for more detail. Copilot can add code snippets into the draft to improve clarity and provide immediate context for these issues.

4. Repeat this process for other issues in the epic, refining descriptions and breaking down tasks as needed.

5. Once you’re satisfied with the issue descriptions, click **Create all** to create the issues in your repository.

## Unlink issues

If Copilot generates a sub-issue that doesn't belong to the issue tree, you can unlink it from the issue tree.

1. In the workbench issue tree, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="More options" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg> next to the sub-issue, then click **Unlink sub-issue**.
2. The issue will be unlinked from its parent and will no longer appear under that epic in the tree.

## Next steps

Now that you’ve generated and refined your project issues, you can assign them to the right team members or even to Copilot itself for further assistance. To learn more about how to assign Copilot or contributors to issues, and how to continue planning and implementing your project with Copilot’s agentic features, see [Asking GitHub Copilot to create a pull request](/en/copilot/how-tos/use-copilot-agents/coding-agent/assign-copilot-to-an-issue).

## Further reading

* [Using GitHub Copilot to create or update issues](/en/copilot/how-tos/use-copilot-for-common-tasks/use-copilot-to-create-or-update-issues)
* [Piloting GitHub Copilot coding agent in your organization](/en/copilot/tutorials/coding-agent/pilot-coding-agent)
* [Best practices for using GitHub Copilot to work on tasks](/en/copilot/tutorials/coding-agent/get-the-best-results)
* [Speeding up development work with GitHub Copilot Spaces](/en/copilot/tutorials/speed-up-development-work)
