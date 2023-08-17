# Contributing to the playbook

Contributions from the team are always welcome! This playbook is currently in alpha, meaning we're testing out what content and guidance is useful. Raising issues and pull requests is strongly encouraged, so that we can develop the playbook as a team.

We continually update this playbook because we're always looking for better ways to get things done. And that changes over time, especially as who works on the team and what we work on changes too.

This document is a guide on contributing to the team docs. It is a live guide and may not be complete, so you can raise problems or queries with a delivery manager or product manager.

## Who can contribute

Contributions must come from people on the GOV.UK Design System team. They are the users of these docs and the subject matter experts.

## What to contribute

This playbook is for you. It's a reference, a set of docs to turn to when you're unsure about something, so contribute anything that will help you in your day job. 

Step-by-step guides on how to do things and our processes are good. Models, principles, ways of thinking and examples are great. It helps us learn what we do, and how and why we do it.

## How to contribute

How you contribute will depend on your familiarity with working on GitHub, but contributing to the playbook is a safe way to build your skills. 

### 1. Using a text editor

Most people are familiar with text editors like Notepad, Google Docs, Microsoft Word or Notion. You can use whatever is most familiar to you to make a contribution.

Write your contribution and share the document with someone on the team for feedback.

When your document is ready to be published, seek help from a developer or designer to raise a pull request.

### 2. Using the GitHub file editor

You can create and edit files using the GitHub file editor. Most files can be found in their corresponding folder inside the `/source/` folder. For example, files describing our support processes can be found in `/source/support` folder.

You can follow GitHub's detailed guides on [creating new files](https://docs.github.com/en/repositories/working-with-files/managing-files/creating-new-files) and [editing files](https://docs.github.com/en/repositories/working-with-files/managing-files/editing-files) to create or edit a file. 

### 3. Using a GitHub Codespace

A GitHub Codespace allows you to work on a copy of the playbook on a virtual machine, meaning you don't have to download any files or tools to your machine. It's useful if you've got a locked-down machine. You will use Visual Studio Code and the terminal to create and edit files, and it's easy to get started. 

- In a new tab, visit the []`design-system-team-docs` repository](https://github.com/alphagov/design-system-team-docs) and follow GitHub's guide on [creating a Codespace for a repository](https://docs.github.com/en/codespaces/developing-in-codespaces/creating-a-codespace-for-a-repository#creating-a-codespace-for-a-repository).
- Once the Codespace is ready, you will see the Terminal tab is open. It will say something like `@yourgithubusername ➜ /workspaces/design-system-team-docs (branch-name)`. 
- Type in `gem install middleman` and press Enter. If it's successful, you'll see `Successfully installed middleman`.
- Type in `bundle install`. If it's successful, you'll see `Bundle complete!`
- Type in `bundle exec middleman server` and press Enter. If it's successful, you should see a dialog pop up. Click the `Open in browser` button.

A new tab will open which shows a preview of the team docs. You can now create and edit `.html.md.erb` files to add to and edit the docs. Your changes will save automatically but you will need to [commit your changes](https://docs.github.com/en/codespaces/developing-in-codespaces/using-source-control-in-your-codespace#committing-your-changes) to save them for good. 

After you've made all the changes and additions you intended to make, [raise a pull request](https://docs.github.com/en/codespaces/developing-in-codespaces/using-source-control-in-your-codespace#raising-a-pull-request).

Ask one of our friendly developers for help if you're doing this for the first time. Ask them if they would be happy to help in future too!

### 4. Using your machine

If you choose this option, you probably know how to do it. Create a branch, commit changes and raise a pull request. Your pull request will be reviewed and approved when ready. You can merge your pull request once approved.

### 5. Create an issue

You can also create an issue to suggest additions and changes without working directly on the files. Add a new issue via the [Issues view](https://github.com/alphagov/design-system-team-docs/issues) to suggest documentation for the playbook.

## Need help?

Ask your team-mates in the team Slack channel, someone will reply and help out.