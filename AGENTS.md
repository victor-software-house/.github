# .github

This repository holds the organization's default pull request template, `.github/pull_request_template.md`.
GitHub fills it into every new pull request in a repository of the organization that has no template of its own, private repositories included.

1. The repository must stay public for GitHub to apply the template, so it holds nothing private: no people, plans, boards, or links to private repositories.
2. A repository's own `.github/pull_request_template.md` overrides the default.
3. Changes reach `main` through a pull request, merged with a merge commit.
4. The template's `##` headings are the sections every pull request body must fill, and `.github/workflows/pr-template.yml` checks them in every repository the organization ruleset "main: pull request before merge (code repos)" covers.  
   A heading added to the template is required in every repository at once, so an optional section goes in a comment.  
   The ruleset pins the workflow by commit, so a change to it takes effect when the ruleset's pin moves to the merge commit.
