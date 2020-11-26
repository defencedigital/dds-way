# The DDS Way

[The DDS Way](https://defencedigital.github.io/dds-way/) is a format borrowed from the [GDS Way](https://gds-way.cloudapps.digital/) and outlines the way that we, the Defence Digital Service (DDS) work. It's a working document and instructions as to how you can contribute are below. Elements are also borrowed from the [Ministry of Justice Technical Guidance](https://ministryofjustice.github.io/technical-guidance/)

## How it works

The DDS Way is built using [MkDocs](https://www.mkdocs.org/), using the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme. 

Basically, it works by creating a markdown file, which MkDocs then uses to generate a flat HTML file based on the stylesheets that the theme defines, and then uses the folder structure to create the structure of the static website. 

In the case of the DDS Way, all of those markdown files are created and edited on the `main` branch of this repository. [GitHub Actions](), triggered by a merge to that `main` branch, initiates MkDocs to generate those static files and pushes them to a `gh-pages` branch. [GitHub Pages]() is then configured to serve all files on that branch to the DDS Way URL (https://defencedigital.github.io/). 

## How to contribute

**TL;DR** – raise a PR, making changes based on the `main` branch. These changes will be continuously deployed to the `gh-pages` branch, once the PR has been accepted. 

1. As these things usually begin, [clone](https://github.com/git-guides/git-clone) this repository to your local machine. 

2. Next, [switch to a new branch](https://stackoverflow.com/questions/17958288/branch-and-checkout-using-a-single-command), which you should name something descriptive.

3. Make changes to existing markdown files, or add new markdown files (which must have a `.md` file extension) and produce the content you would like to appear in the DDS Way. This [Markdown Guide](https://www.markdownguide.org/) can help you with how to format those files. 

4. [Commit your changes](https://github.com/git-guides/git-commit) to your branch, ensuring that you leave a meaningful commit message.

5. [Push your changes](https://docs.github.com/en/free-pro-team@latest/github/using-git/pushing-commits-to-a-remote-repository) to this repository. You'll probably be told that [there's no upstream branch](https://stackoverflow.com/questions/37770467/why-do-i-have-to-git-push-set-upstream-origin-branch) – just follow the instructions. 

6. Jump into this repository, where you'll be prompted to [raise a pull request (PR)](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) based on your changes, and raise that PR!

7. Someone in DDS will see the PR and review the changes, at which point (if accepted) our [CI/CD](https://www.redhat.com/en/topics/devops/what-is-ci-cd) pipeline will apply your changes to the DDS Way. Feel free to [ping us on Slack](https://defencedigital.slack.com/messages/dds-way/), if you think your PR needs some quicker attention. 

That's it! Any questions, either [grab us on Slack](https://defencedigital.slack.com/messages/dds-way/) or send us an email at [team@digital.mod.uk](mailto:team@digital.mod.uk?subject=dds-way)