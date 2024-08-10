<div align="center">

<div align="center">


<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://codium.ai/images/pr_agent/logo-dark.png" width="330">
  <source media="(prefers-color-scheme: light)" srcset="https://codium.ai/images/pr_agent/logo-light.png" width="330">
  <img src="https://codium.ai/images/pr_agent/logo-light.png" alt="logo" width="330">

</picture>
<br/>
CodiumAI PR-Agent aims to help efficiently review and handle pull requests, by providing AI feedback and suggestions
</div>

[![GitHub license](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://github.com/Codium-ai/pr-agent/blob/main/LICENSE)
[![Static Badge](https://img.shields.io/badge/Chrome-Extension-violet)](https://chromewebstore.google.com/detail/pr-agent-chrome-extension/ephlnjeghhogofkifjloamocljapahnl)
[![Static Badge](https://img.shields.io/badge/Code-Benchmark-blue)](https://pr-agent-docs.codium.ai/finetuning_benchmark/)
[![Discord](https://badgen.net/badge/icon/discord?icon=discord&label&color=purple)](https://discord.com/channels/1057273017547378788/1126104260430528613)
[![Twitter](https://img.shields.io/twitter/follow/codiumai)](https://twitter.com/codiumai)
[![Cheat Sheet](https://img.shields.io/badge/Cheat-Sheet-red)](https://www.codium.ai/images/pr_agent/cheat_sheet.pdf)
    <a href="https://github.com/Codium-ai/pr-agent/commits/main">
    <img alt="GitHub" src="https://img.shields.io/github/last-commit/Codium-ai/pr-agent/main?style=for-the-badge" height="20">
    </a>
</div>

### [Documentation](https://pr-agent-docs.codium.ai/)
- See the [Installation Guide](https://pr-agent-docs.codium.ai/installation/) for instructions on installing PR-Agent on different platforms.

- See the [Usage Guide](https://pr-agent-docs.codium.ai/usage-guide/) for instructions on running PR-Agent tools via different interfaces, such as CLI, PR Comments, or by automatically triggering them when a new PR is opened.

- See the [Tools Guide](https://pr-agent-docs.codium.ai/tools/) for a detailed description of the different tools, and the available configurations for each tool.


## Table of Contents
- [News and Updates](#news-and-updates)
- [Overview](#overview)
- [Example results](#example-results)
- [Try it now](#try-it-now)
- [PR-Agent Pro 💎](#pr-agent-pro-)
- [How it works](#how-it-works)
- [Why use PR-Agent?](#why-use-pr-agent)
  
## News and Updates

### August 5, 2024
Added support for [GitLab pipeline](https://pr-agent-docs.codium.ai/installation/gitlab/#run-as-a-gitlab-pipeline) - you can now run easily PR-Agent as a GitLab pipeline, without needing to set up your own server.

### July 28, 2024

(1) improved support for bitbucket server - [auto commands](https://github.com/Codium-ai/pr-agent/pull/1059) and [direct links](https://github.com/Codium-ai/pr-agent/pull/1061)

(2) custom models are now [supported](https://pr-agent-docs.codium.ai/usage-guide/changing_a_model/#custom-models)

### July 6, 2024

v0.23 has been released. See full log changes [here](https://github.com/Codium-ai/pr-agent/releases/tag/v0.23).

### July 4, 2024

Added improved support for claude-sonnet-3.5 model (anthropic, vertex, bedrock), including dedicated prompts.

### June 17, 2024

New option for a self-review checkbox is now available for the `/improve` tool, along with the ability(💎) to enable auto-approve, or demand self-review in addition to human reviewer. See more [here](https://pr-agent-docs.codium.ai/tools/improve/#self-review).

<kbd><img src="https://www.codium.ai/images/pr_agent/self_review_1.png" width="512"></kbd>

### June 6, 2024

New option now available (💎) - **apply suggestions**:

<kbd><img src="https://www.codium.ai/images/pr_agent/apply_suggestion_1.png" width="512"></kbd>

&rarr;

<kbd><img src="https://www.codium.ai/images/pr_agent/apply_suggestion_2.png" width="512"></kbd>



## Overview
<div style="text-align:left;">

Supported commands per platform:

|       |                                                                                                         | GitHub             | Gitlab             | Bitbucket          | Azure DevOps |
|-------|---------------------------------------------------------------------------------------------------------|:--------------------:|:--------------------:|:--------------------:|:------------:|
| TOOLS | Review                                                                                                  | ✅ | ✅ | ✅ |      ✅       |
|       | ⮑ Incremental                                                                                           | ✅ |                    |                    |              |
|       | ⮑ [SOC2 Compliance](https://pr-agent-docs.codium.ai/tools/review/#soc2-ticket-compliance) 💎            | ✅ | ✅ | ✅ |              |
|       | Describe                                                                                                | ✅ | ✅ | ✅ |      ✅       |
|       | ⮑ [Inline File Summary](https://pr-agent-docs.codium.ai/tools/describe#inline-file-summary) 💎          | ✅ |                    |                    |              |
|       | Improve                                                                                                 | ✅ | ✅ | ✅ |      ✅       |
|       | ⮑ Extended                                                                                              | ✅ | ✅ | ✅ |      ✅       |
|       | Ask                                                                                                     | ✅ | ✅ | ✅ |      ✅       |
|       | ⮑ [Ask on code lines](https://pr-agent-docs.codium.ai/tools/ask#ask-lines)                              | ✅ | ✅ |                    |              |
|       | [Custom Prompt](https://pr-agent-docs.codium.ai/tools/custom_prompt/) 💎                                | ✅ | ✅ | ✅ |              |
|       | [Test](https://pr-agent-docs.codium.ai/tools/test/) 💎                                                  | ✅ | ✅ |                    |              |
|       | Reflect and Review                                                                                      | ✅ | ✅ | ✅ |      ✅       |
|       | Update CHANGELOG.md                                                                                     | ✅ | ✅ | ✅ |      ✅       |
|       | Find Similar Issue                                                                                      | ✅ |                    |                    |              |
|       | [Add PR Documentation](https://pr-agent-docs.codium.ai/tools/documentation/) 💎                         | ✅ | ✅ |                   |              |
|       | [Custom Labels](https://pr-agent-docs.codium.ai/tools/custom_labels/) 💎                                | ✅ | ✅ |                    |              |
|       | [Analyze](https://pr-agent-docs.codium.ai/tools/analyze/) 💎                                            | ✅ | ✅ |                    |              |
|       | [CI Feedback](https://pr-agent-docs.codium.ai/tools/ci_feedback/) 💎                                    | ✅ |                    |                    |              |
|       | [Similar Code](https://pr-agent-docs.codium.ai/tools/similar_code/) 💎                                  | ✅ |                    |                    |              |
|       |                                                                                                         |                    |                    |                    |              |
| USAGE | CLI                                                                                                     | ✅ | ✅ | ✅ |      ✅       |
|       | App / webhook                                                                                           | ✅ | ✅ | ✅ |      ✅       |
|       | Tagging bot                                                                                             | ✅ |                    |                    |              |
|       | Actions                                                                                                 | ✅ |                    | ✅ |              |
|       |                                                                                                         |                    |                    |                    |              |
| CORE  | PR compression                                                                                          | ✅ | ✅ | ✅ |      ✅       |
|       | Repo language prioritization                                                                            | ✅ | ✅ | ✅ |      ✅       |
|       | Adaptive and token-aware file patch fitting                                                             | ✅ | ✅ | ✅ |      ✅       |
|       | Multiple models support                                                                                 | ✅ | ✅ | ✅ |      ✅       |
|       | [Static code analysis](https://pr-agent-docs.codium.ai/core-abilities/#static-code-analysis) 💎         | ✅ | ✅ | ✅ |              |
|       | [Global and wiki configurations](https://pr-agent-docs.codium.ai/usage-guide/configuration_options/) 💎 | ✅ | ✅ | ✅ |              |
|       | [PR interactive actions](https://www.codium.ai/images/pr_agent/pr-actions.mp4) 💎                       | ✅ |        ✅           |                    |              |
- 💎 means this feature is available only in [PR-Agent Pro](https://www.codium.ai/pricing/)

[//]: # (- Support for additional git providers is described in [here]&#40;./docs/Full_environments.md&#41;)
___

‣ **Auto Description ([`/describe`](https://pr-agent-docs.codium.ai/tools/describe/))**: Automatically generating PR description - title, type, summary, code walkthrough and labels.
\
‣ **Auto Review ([`/review`](https://pr-agent-docs.codium.ai/tools/review/))**: Adjustable feedback about the PR, possible issues, security concerns, review effort and more.
\
‣ **Code Suggestions ([`/improve`](https://pr-agent-docs.codium.ai/tools/improve/))**: Code suggestions for improving the PR.
\
‣ **Question Answering ([`/ask ...`](https://pr-agent-docs.codium.ai/tools/ask/))**: Answering free-text questions about the PR.
\
‣ **Update Changelog ([`/update_changelog`](https://pr-agent-docs.codium.ai/tools/update_changelog/))**: Automatically updating the CHANGELOG.md file with the PR changes.
\
‣ **Find Similar Issue ([`/similar_issue`](https://pr-agent-docs.codium.ai/tools/similar_issues/))**: Automatically retrieves and presents similar issues.
\
‣ **Add Documentation 💎  ([`/add_docs`](https://pr-agent-docs.codium.ai/tools/documentation/))**: Generates documentation to methods/functions/classes that changed in the PR.
\
‣ **Generate Custom Labels 💎 ([`/generate_labels`](https://pr-agent-docs.codium.ai/tools/custom_labels/))**: Generates custom labels for the PR, based on specific guidelines defined by the user.
\
‣ **Analyze 💎 ([`/analyze`](https://pr-agent-docs.codium.ai/tools/analyze/))**: Identify code components that changed in the PR, and enables to interactively generate tests, docs, and code suggestions for each component.
\
‣ **Custom Prompt 💎 ([`/custom_prompt`](https://pr-agent-docs.codium.ai/tools/custom_prompt/))**: Automatically generates custom suggestions for improving the PR code, based on specific guidelines defined by the user.
\
‣ **Generate Tests 💎 ([`/test component_name`](https://pr-agent-docs.codium.ai/tools/test/))**: Generates unit tests for a selected component, based on the PR code changes.
\
‣ **CI Feedback 💎 ([`/checks ci_job`](https://pr-agent-docs.codium.ai/tools/ci_feedback/))**: Automatically generates feedback and analysis for a failed CI job.
\
‣ **Similar Code 💎 ([`/find_similar_component`](https://pr-agent-docs.codium.ai/tools/similar_code/))**: Retrieves the most similar code components from inside the organization's codebase, or from open-source code.
___

<hr>



## How it works

The following diagram illustrates PR-Agent tools and their flow:

![PR-Agent Tools](https://codium.ai/images/pr_agent/diagram-v0.9.png)

Check out the [PR Compression strategy](https://pr-agent-docs.codium.ai/core-abilities/#pr-compression-strategy) page for more details on how we convert a code diff to a manageable LLM prompt

## Why use PR-Agent?

A reasonable question that can be asked is: `"Why use PR-Agent? What makes it stand out from existing tools?"`

Here are some advantages of PR-Agent:

- We emphasize **real-life practical usage**. Each tool (review, improve, ask, ...) has a single GPT-4 call, no more. We feel that this is critical for realistic team usage - obtaining an answer quickly (~30 seconds) and affordably.
- Our [PR Compression strategy](https://pr-agent-docs.codium.ai/core-abilities/#pr-compression-strategy)  is a core ability that enables to effectively tackle both short and long PRs.
- Our JSON prompting strategy enables to have **modular, customizable tools**. For example, the '/review' tool categories can be controlled via the [configuration](pr_agent/settings/configuration.toml) file. Adding additional categories is easy and accessible.
- We support **multiple git providers** (GitHub, Gitlab, Bitbucket), **multiple ways** to use the tool (CLI, GitHub Action, GitHub App, Docker, ...), and **multiple models** (GPT-4, GPT-3.5, Anthropic, Cohere, Llama2).


## Data privacy

### Self-hosted PR-Agent

- If you host PR-Agent with your OpenAI API key, it is between you and OpenAI. You can read their API data privacy policy here:
https://openai.com/enterprise-privacy
