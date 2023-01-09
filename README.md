# Semantic version release manager

[![CI](https://github.com/deeagle/semantic-release-with-github/workflows/CI/badge.svg)](https://github.com/deeagle/semantic-release-with-github/actions?query=workflow:CI+branch:master)
[![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)

It's a test repo to get the semantic-release manager into github-actions.

Semantic-release is a nodejs tool and I want to see it working
with a non-js language in ci.

## How does it works

- You have to enable and configure [Pull-Requests-Plugin](https://github.com/apps/semantic-pull-requests)
  for your repo:
  - it will check if your commit names are correct for semantic versions
    - The pull-request commit have to be in the semantic version,
      otherwise nothing happens
    - the DEFAULT name is like *"Merge pull request #7 from some/nice/branch"*  
    - for further details see: [semantic-release/commit-analyzer](https://github.com/semantic-release/commit-analyzer/).
  - NodeJS
    - The nodejs stuff (like package installs) is in the workflows
      file and nobody have to install it locally. :)
    - The workflow token `GITHUB_TOKEN` will be filled by GitHub
      (it's a gift and default ;))

## Deficits

The plugin has problems outputting the current and next version number outside
the release. There are many possible workarounds, as the developers probably
see it differently (see [project issue](https://github.com/semantic-release/semantic-release/issues/753)].
It is also very good that under Github the pull request is the standard, which
of course is not supported by the software (see [Action](https://github.com/deeagle/semantic-release-with-github/runs/6076484877?check_suite_focus=true)).

<!-- markdownlint-disable MD013 -->
```bash
...
[10:46:49 AM] [semantic-release] › ℹ  This run was triggered by a pull request and therefore a new version won't be published.
...
```
<!-- markdownlint-enable MD013 -->

Why could it be useful?
The version tag would be useful for me to automatically build containers
after release with different tags, for example. This should be possible,
but has to be tested unattractively with a new project.

## Docker-Compose and PHP code

- It's only a demo project and includes some tests, especially for the CI.
- if you want to run something on your machine, e.g. some commands for you:
  - `docker-compose run composer composer --version`
  - `docker-compose run php php --version`
  - `docker-compose run phpunit phpunit --version`
