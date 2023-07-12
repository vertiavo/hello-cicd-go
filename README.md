# hello-cicd-go

Repository with simple CI/CD configuration for Go.

## CI

This repo uses Github Actions to check if repository is following Go language standards.

To achieve that, two jobs are executed:

- build-verify-test (uses pre-commit-ci/lite-action)
  - trailing-whitespace
  - end-of-file-fixer
  - check-yaml
  - check-added-large-files
  - go-build-mod
  - go-mod-tidy
  - go-test-mod
  - go-revive
  - go-staticcheck
  - go-imports
- golangci (uses golangci/golangci-lint-action)

When those steps finish successfully another action (anothrNick/github-tag-action) creates and pushes new tag.
