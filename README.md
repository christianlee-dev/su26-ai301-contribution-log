# Contribution 1: Add plain-English use cases to the README and docs landing page  

**Contribution Number:** 1  
**Student:** Christian Lee  
**Issue:** https://github.com/seraph-quest/seraph/issues/211  
**Status:** [Phase II] [In Progress]

---

## Why I Chose This Issue

I'm choosing Seraph GitHub Issue #211, titled "Add plain-English use cases to the README and docs landing page," because it's the simplest issue I could find that's still interesting to me. As someone just starting out in Open Source Software (OSS) development, I wanted to start with learning the basic fork-change-PR methodology that real OSS developers use in day-to-day workflows.

In addition to getting to learn the ropes, I'm also interested in writing documentation to make software more approachable to first-time users. I've handled writing documentation in the form of cybersecurity writeups in school, so I believe this will be a great entry point for me.

From reading the repository, I understand that this software, titled "Seraph," is an AI assistant tool designed to handle everyday tasks, increasing efficiency. The issue wants to add use cases for anyone using this software, in both the README and the documentation landing page, which can be found in docs/implementation/00-master-roadmap.md.

From reading CONTRIBUTING.md, I understand that my pull requests should never target the develop or main branches directly, and should instead point toward a branch off of develop/feat or develop/fix. In my case, my PR will likely target the develop/fix branch, since my changes aim to fix an issue in the README and landing page, instead of adding an entirely new feature.

As of now, the maintainer has not responded to my intro statement on the issue page, but the GitHub repo has seen activity since about three weeks ago, so I am somewhat confident that my changes will see some use, even if they are not ultimately merged into the main repository.

---

## Understanding the Issue

### Problem Description

"Seraph" is an AI assistant tool designed to handle everyday tasks, as described in the previous section. As such, it would be useful for users of this tool to know some basic use-cases upon starting it. However, such use cases are not present in the README or the documentation landing page, which are two of the most common places that users of this software are likely to visit. Knowing exactly what Seraph can and cannot do could prove invaluable for users who would like to integrate LLMs into their daily workflow.

### Expected Behavior

Upon cloning the repo to one's own machine, or otherwise visiting the Seraph repository, one should see basic use-cases in plain English demonstrating outcome-first operations that Seraph is able to provide to the user. Additionally, one can spin up the backend interface and visit the /docs endpoint to see the documentation landing page, and see the use-cases mirrored from the README.

### Current Behavior

Upon cloning the repository, a user will not be able to see plain English use cases of the Seraph AI agent interface. The same can be said upon visiting the backend documentation landing page.

### Affected Components

To the best of my knowledge, this issue seems to affect the main README.md file, as well as the docs/implementation/00-master-roadmap.md file, since these both contain information about the Seraph AI agent in great detail, yet do not include plain-English use cases.

---

## Reproduction Process

### Environment Setup

After cloning the repository, one should enable Git symlinks and place the folder outside of the OneDrive folder (if the user is running Windows). Additionally, one should install Docker Desktop for added convenience.

### Steps to Reproduce

1. Copy env.dev.example to .env.dev and configure with an OpenRouter API key.
2. Build by running ./manage.sh -e dev build on Git Bash.
3. Launch by running ./manage.sh -e dev up -d on Git Bash.
4. Visit frontend http://localhost:3000 to check that the frontend is accessible.
5. Visit backend http://localhost:8004/docs to see the backend documentation landing page.
6. Observe that the README.md and the docs landing page do not contain use cases of the Seraph AI agent in plain English.

### Reproduction Evidence

- **Commit showing reproduction:** A reproduction commit doesn't seem necessary, since my issue concerns itself with the absence of text from documentation. You can already see use cases absent from the current repository's README.md.
- **Screenshots/logs:** https://imgur.com/a/9A8h38j
- **My findings:** In this specific repo, the ./manage.sh script handles all the building, running, and log recording. Instead of navigating to specific log files in File Explorer, one can run ./manage.sh -e dev logs to view the log files and/or output them to a separate file for further analysis.

---

## Solution Approach

### Analysis

The root issue comes from the file hosting the backend server, backend/src/app.py, as well as the README.md file itself. The problem seems to come from the fact that, upon starting up the backend server, there is no "description" attribute to the FastAPI app.

### Proposed Solution

In backend/src/app.py, in the lines that describe the FastAPI app definition, I will include an attribute named "description" containing a string that includes use cases for the Seraph AI agent. I will also mirror this list of plain-English use cases to the main README.md file, so that it is visible instantly upon viewing the repository. I will make sure these use cases are outcome-first, rather than architecture-first, as stated on the GitHub issue.

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** Plain-English use cases are absent from the repository of the AI agent Seraph's README.md file, as well as the backend docs landing page.

**Match:** This is similar to a documentation-oriented problem, and involves me having to add resources or, in this case, use cases for an AI agent, that other users of the Seraph AI agent will find helpful.

**Plan:** [Step-by-step implementation plan]
1. Modify the file backend/src/app.py to include a description attribute that showcases use cases of the Seraph AI agent.
2. Restart the backend docs landing page as necessary, and confirm that plain-English use cases appear at the top of the page, and are outcome-first, instead of architecture-first.
3. Copy this list of use cases to the main README.md file.
4. Confirm all tests succeed to ensure that nothing else has been broken.

**Implement:** [Link to your branch/commits as you work]

**Review:** [Self-review checklist - does it follow the project's contribution guidelines?]

**Evaluate:** [How will you verify it works?]

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
