# .github

This repository holds the organization's default pull request template, `.github/pull_request_template.md`.
GitHub fills it into every new pull request in a repository of the organization that has no template of its own, private repositories included.

1. The repository must stay public for GitHub to apply the template, so it holds nothing private: no people, plans, boards, or links to private repositories.
2. A repository's own `.github/pull_request_template.md` overrides the default.
3. Changes reach `main` through a pull request, merged with a merge commit.
4. The template's `##` headings are the sections every pull request body must fill, and `.github/workflows/pr-template.yml` checks them in every repository the organization ruleset "main: pull request before merge (code repos)" covers.  
   A heading added to the template is required in every repository at once, so an optional section goes in a comment.
5. The ruleset runs that workflow from `main` (operator, 2026-11-11), so a change to it reaches every repository when it merges.
6. The same workflow's `PR prose` job lints each pull request's title and body with the ProseStyle and PullRequestStyle packages, at the levels every repository shares.
7. A pull request here runs `main`'s copy of `pr-template.yml`, never the one it changes.
   - The `Check` workflow runs from the pull request's branch.  
     It lints the workflows and compiles each `actions/github-script` step.
   - The repository ruleset "main: Workflow check" requires it.
   - A script that does not compile on `main` fails every pull request in the organization, this repository's own included.  
     Only an organization admin can then merge the fix.
