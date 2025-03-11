# 📜 **Contributing Guidelines**

We welcome contributions from everyone in the **Grimwald SMP** community! Whether you’re helping improve documentation, fixing typos, or adding new content, we appreciate your efforts. Please follow these guidelines to ensure consistency and quality across the knowledge base.

# **1. General Guidelines**

- All contributions should align with the **Grimwald Knowledge Base** standards. Review the [Documentation Standards](standards.md) before contributing.
- Contributions must be **respectful** and **objective**, adhering to the community’s values.
- **Do not mention** players or staff members by their **real or online names** in any documentation or contributions.

# **2. Using GitHub for Contributions**

Grimwald's Knowledge Base is hosted on **GitHub**. To contribute, please follow these steps:
A **GitHub Account** and having **Git** installed are necessary before continuing.
Prior knowledge of **GitHub** and **Git** will be helpful but are not required.

## **Forking the Repository**

1. Visit the **Grimwald Knowledge Base** repository on GitHub.
2. Click on the **Fork** button in the top-right corner to create a copy of the repository under your GitHub account.

## **Making Changes**

1. Clone your forked repository to your local machine: `git clone https://github.com/Grimwald-SMP/grimwald-knowledge-base.git`
2. Navigate to the project directory: `cd grimwald-knowledge-base`
3. Create a new branch for your changes: `git checkout -b your-feature-branch`
4. Make the necessary changes in your local copy. Follow the Documentation Standards for formatting and writing guidelines.
5. Test your changes locally (see section on MkDocs below).

## **Submitting a Pull Request**
Once your changes are complete:

1. Commit your changes: `git add .` `git commit -m "Description of changes made"`
2. Push your branch to your forked respository: `git push origin your-feature-branch`
3. Go to the GitHub Repostory and create a **Pull Request (PR)** from your branch to the main repositories `develop` branch.
4. Ensure your PR:
    - Includes edits to the `changelog.md` file explaining your changes.
    - Adheres to the standards.

Admins will review the PR, and after any necessary revisions, your changes will be merged into the main repository.

# **3. Working with MkDocs**

The Grimwald Knowledge Base is built using **MkDocs**. To view and preview your changes locally, follow these steps:

## **Installing MkDocs**

- If you haven't already you will need to install python on your machine. [Download on Python.org](https://www.python.org/downloads/)
- If you haven't already installed MkDocs, you can do so by running: `pip install mkdocs`

## **Running the Development Server**
To preview your changes locally, you need to run the development server:

1. Navigate to your forked repository's root directory: `cd grimwald-knowledge-base`
2. Start the MkDocs development server: `mkdocs serve`
3. Visit [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser to preview the documentation.

## **Building and deploying the Docs**
If you are an admin you will also need to know how to **build and deploy** the docs.
You should build and deploy **after every change to develop**. If you are an admin and are the one making or the one who reviewed and accepted the changes you are responsible for doing this yourself.

- After merging the required changes from a PR into the `main` branch, Run the following command to build the documentation into a static site and deploy it to **GitHub Pages**: `mkdocs gh-deploy`.
- **Warning** Using this command will deploy the site from your local branch, including changes that have not been commited, **delete or stash changes** first.

## **Dealing with Merge Conflicts**
If there are merge conflicts:
- Make sure you pull the latest changes from the main repostitory: `git pull origin main`
- Resolve the conflicts and push the changes.

# **5. Additional Notes**

- Please **refrain from editing** brand-related documents or documents relating to Grimwald's core identity and values unless you have been explicitly told to by an admin, If you are an admin you should make sure the owner(s) are ok with this change. This applies to major changes and not fixes such as correcting typos.
- Keep your pull requests small and focused on a single task or feature. This makes them easier to review and less prone to errors.
- Always test your changes locally to ensure everything is working as expected before submitting your PR.
- Bare in mind if you build the docs locally, they may not behave as expected when opening the html files as some features do not work until they are hosted on a server, Instead you should stick to viewing them on the development server.

By following these guidelines, you ensure that Grimwald’s Knowledge Base remains organized, up-to-date, and helpful to all users.