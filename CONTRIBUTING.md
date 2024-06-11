# Contributing to this project

First off, thanks for taking the time to contribute! ❤️

All types of contributions are encouraged and valued. See the [Table of Contents](#table-of-contents) for different ways to help and details about how this project handles
them. Please make sure to read the relevant section before making your contribution. It will make it a lot easier for us maintainers and smooth out the experience for all
involved. The community looks forward to your contributions. 🎉

And if you like the project, but just don't have time to contribute, that's fine. There are other easy ways to support the project and show your appreciation, which we would
also be very happy about:

- Star the project
- Tweet about it
- Refer this project in your project's [README.md](README.md)
- Mention the project at local meetups and tell your friends/colleagues

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [I Have a Question](#i-have-a-question)
- [I Want To Contribute](#i-want-to-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Your First Code Contribution](#your-first-code-contribution)
  - [Improving The Documentation](#improving-the-documentation)
- [Style Guides](#style-guides)
  - [Commit Messages](#commit-messages)
  - [Markdown](#markdown)
  - [Ansible](#ansible)
  - [Spelling](#spelling)

## Code of Conduct

This project and everyone participating in it is governed by the [Code of Conduct](CODE_OF_CONDUCT.md).
By participating, you are expected to uphold this code. Please report unacceptable behavior to <github@scheib.xyz>.

## I Have a Question

> If you want to ask a question, we assume that you have read the available [Documentation](README.md)

Before you ask a question, it is best to search for existing [Issues](https://github.com/sscheib/ansible-role-openwrt_extroot/issues) that might help you. In case you have found a
suitable issue and still need clarification, you can write your question in this issue. It is also advisable to search the internet for answers first.

If you then still feel the need to ask a question and need clarification, we recommend the following:

- Open an [Issue](https://github.com/sscheib/ansible-role-openwrt_extroot/issues/new).
- Provide as much context as you can about what you're running into.
- Provide project and platform versions (`OpenWrt` version, Ansible version, version of this role), depending on what seems relevant.

We will then take care of the issue as soon as possible.

## I Want To Contribute

### Legal Notice

When contributing to this project, you must agree that you have authored 100% of the content, that you have the necessary rights to the content and that the content you
contribute may be provided under the project license.

### Reporting Bugs

#### Before Submitting a Bug Report

A good bug report shouldn't leave others needing to chase you up for more information. Therefore, we ask you to investigate carefully, collect information and describe the issue
in detail in your report. Please complete the following steps in advance to help us fix any potential bug as fast as possible.

- Make sure that you are using the latest version.
- Determine if your bug is really a bug and not an error on your side e.g. using incompatible environment components/versions
  (Make sure that you have read the [documentation](README.md). If you are looking for support, you might want to check [this section](#i-have-a-question)).
- To see if other users have experienced (and potentially already solved) the same issue you are having, check if there is not already a bug report existing for your bug
  or error in the [bug tracker](https://github.com/sscheib/ansible-role-openwrt_extroot/issues).
- Also make sure to search the internet (including Stack Overflow) to see if users outside of the GitHub community have discussed the issue.
- Collect information about the bug:
  - Stack trace (Traceback)
  - OS, Platform and Version (Windows, Linux, macOS, x86, ARM, etc.)
  - Version of the interpreter, runtime environment, package manager, depending on what seems relevant.
  - Possibly your input and the output
  - Can you reliably reproduce the issue? And can you also reproduce it with older versions?

#### How Do I Submit a Good Bug Report?

> You must never report security related issues, vulnerabilities or bugs including sensitive information to the issue tracker, or elsewhere in public. Instead sensitive bugs
must be sent by email to <github@scheib.xyz>.

We use GitHub issues to track bugs and errors. If you run into an issue with the project:

- Open an [Issue](https://github.com/sscheib/ansible-role-openwrt_extroot/issues/new). (Since we can't be sure at this point whether it is a bug or not, we ask you not to talk
  about a bug yet and not to label the issue.)
- Explain the behavior you would expect and the actual behavior.
- Please provide as much context as possible and describe the *reproduction steps* that someone else can follow to recreate the issue on their own. This usually includes your
  code. For good bug reports you should isolate the problem and create a reduced test case.
- Provide the information you collected in the previous section.

Once it's filed:

- The project team will label the issue accordingly.
- A team member will try to reproduce the issue with your provided steps. If there are no reproduction steps or no obvious way to reproduce the issue, the team will ask you for those
  steps and mark the issue as `needs-reproducer`. Bugs with the `needs-reproducer` tag will not be addressed until they are reproduced.
- If the team is able to reproduce the issue, it will be marked `needs-fix`, as well as possibly other tags (such as `critical`), and the issue will be left to
  be [implemented by someone](#your-first-code-contribution).

### Suggesting Enhancements

This section guides you through submitting an enhancement suggestion for `ansible-role-openwrt_extroot`, **including completely new features and minor improvements to existing
functionality**. Following these guidelines will help maintainers and the community to understand your suggestion and find related suggestions.

#### Before Submitting an Enhancement

- Make sure that you are using the latest version.
- Read the [documentation](README.md) carefully and find out if the functionality is already covered, maybe by an individual configuration.
- Perform a [search](https://github.com/sscheib/ansible-role-openwrt_extroot/issues) to see if the enhancement has already been suggested. If it has, add a comment to the existing
  issue instead of opening a new one.
- Find out whether your idea fits with the scope and aims of the project. It's up to you to make a strong case to convince the project's developers of the merits of this feature.
  Keep in mind that we want features that will be useful to the majority of our users and not just a small subset. If you're just targeting a minority of users, consider writing
  an add-on/plugin library.

#### How Do I Submit a Good Enhancement Suggestion?

Enhancement suggestions are tracked as [GitHub issues](https://github.com/sscheib/ansible-role-openwrt_extroot/issues).

- Use a **clear and descriptive title** for the issue to identify the suggestion.
- Provide a **step-by-step description of the suggested enhancement** in as many details as possible.
- **Describe the current behavior** and **explain which behavior you expected to see instead** and why. At this point you can also tell which alternatives do not work for you.
- **Explain why this enhancement would be useful** to most `ansible-role-openwrt_extroot` users. You may also want to point out the other projects that solved it better and which
  could serve as inspiration.

### Your First Code Contribution

For your first successful contribution we ask you to follow the following steps:

1. [Fork this repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)
1. Clone your fork to your working machine (`git clone`)
1. Create a new branch using `git checkout -B <your_branch_name>`
1. Set up your development environment using [`pre-commit`](https://pre-commit.com) to ensure that all required continuous integration (CI) workflows succeed when committing and
   pushing your changes. The [documentation of `pre-commit`](https://pre-commit.com/#install) explains how to install it.
1. The `pre-commit` hook `pyspelling` requires [`aspell`](https://github.com/GNUAspell/aspell) to be installed which takes care of spellchecking. *Usually* your system
   provides a package `aspell` ready to install; Please use the package manager of your distribution to install it (e.g. `sudo dnf install aspell`)
1. Once you set up `pre-commit`, run `pre-commit install` **and** `pre-commit install -t commit-msg` which uses the configuration file `.pre-commit-config.yaml` to install the
   required hooks - **inside a Python virtual environment**. Your system will be left untouched.
1. Develop and **test** your code
1. Create a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
1. We will pick it up from here :slightly_smiling_face:

### Improving The Documentation

To improve the documentation, simply raise a
[pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) with the proposed
changes. Please make sure all required continuous integration (CI) workflows succeed - you might want to have a look at [how to contribute code](#your-first-code-contribution) to
learn how to test changes locally prior to submitting a pull request.

## Style Guides

Please try to adhere to the current code and/or documentation to easily "blend in" into existing code and/or documentation.

Below you'll find a little more details about what sort of linting is enforced with which tools. Additionally, the configuration files are referenced, in case you'd like
to understand what configuration is applied to each respective tool.

### Commit Messages

This project makes use and enforces [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).

When contributing code or documentation changes, please ensure to set up your [development environment accordingly](#your-first-code-contribution) which includes
[`commitlint`](https://github.com/conventional-changelog/commitlint) as `pre-commit` hook which will prevent malformed commit messages.

If you are new to Conventional Commits, you might want to consider installing `commitlint-cli` which with our [provided configuration file](.commitlintrc.js) allows for prompting
questions and crafting an appropriate commit message out of your selections.

If you accidentally pushed a commit that does not follow Conventional Commits, the continuous integration (CI) workflow validating commit messages will fail. To correct this, please
refer to [Changing a commit message](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message).

The respective configuration file is [`.commitlintrc.js`](.commitlintrc.js).

### Markdown

Markdown is validated using [`markdown-lint`](https://github.com/DavidAnson/markdownlint). It is included as `pre-commit` hook and continuous integration (CI) workflow in GitHub.
Additionally, links are validated using [`markdown-link-check`](https://github.com/tcort/markdown-link-check); Again, both as `pre-commit` hook and continuous integration (CI)
workflow in GitHub.

The respective configuration files are:

- [`.markdownlint.yml`](.markdownlint.yml) and [`.markdownlintignore`](.markdownlintignore) for `markdown-lint`
- [`.markdown-link-check.json`](.markdown-link-check.json) for `markdown-link-check`

### Ansible

Ansible code is validated using [`ansible-lint`](https://github.com/ansible/ansible-lint) and [`yamllint`](https://github.com/adrienverge/yamllint) (called from `ansible-lint`).
It is included as `pre-commit` hook and continuous integration (CI) workflow in GitHub.

The respective configuration files are [`.ansible-lint`](.ansible-lint) and [`.yamllint`](.yamllint).

### Spelling

We are spellchecking both Ansible code and Markdown files using [`pyspelling`](https://github.com/facelessuser/pyspelling/tree/master).

The respective configuration file is [`.pyspelling.yml`](.pyspelling.yml).

## Attribution

This guide is based on the **contributing-gen**. [Make your own](https://github.com/bttger/contributing-gen)!
