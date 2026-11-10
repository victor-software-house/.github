# .github

Default pull request template for the repositories of this organization.

The pull request template is [`.github/pull_request_template.md`](.github/pull_request_template.md).
GitHub fills it into every new pull request in a repository of the organization that has no template of its own.
A repository's own `.github/pull_request_template.md` overrides it.

[`.github/workflows/pr-template.yml`](.github/workflows/pr-template.yml) checks that a pull request body fills the template.
The organization ruleset "main: pull request before merge (code repos)" requires it in every repository that ruleset covers.
Every `##` heading of the template is a required section: the body has it, in order, with text of its own.
The comments under each heading are guidance, so a section a comment offers, such as Screenshots, is optional.
A pull request an app opens passes, and so does a merge group.
GitHub runs the check on open, push and reopen, so after editing a body, rerun the failed job.
