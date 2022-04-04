# Semantic version release manager

[![CI](https://github.com/deeagle/semantic-release-with-github/workflows/CI/badge.svg)](https://github.com/deeagle/semantic-release-with-github/actions?query=workflow:CI+branch:master)

It's a test repo to get the semantic-release manager into github-actions.

Semantic-release is a nodejs tool and I want to see it working with a non-js language in ci.

## How does it works
- You have to enable and configure [Pull-Requests-Plugin](https://github.com/apps/semantic-pull-requests) for your repo
  - it will check if your commit names are correct for semantic versions
- Attention!
  - The pull-request commit have to be in the semantic version
  - otherwise nothing happens
  - the DEFAULT name is like *"Merge pull request #7 from some/nice/branch"*  
  - for further details see: [semantic-release/commit-analyzer](https://github.com/semantic-release/commit-analyzer/).
- NodeJS
  - The nodejs stuff (like package installs) is in the workflows file and nobody have to install it locally. :)
  - The value *GITHUB_TOKEN* will be filled by github (it's a present and default ;)) 

## Docker-Compose and PHP code
- It's only for some tests, especially for the ci.
- if you want to run something on your machine, e.g.
  - `docker-compose run composer composer --version`
  - `docker-compose run php php --version`
  - `docker-compose run phpunit phpunit --version`