# Semantic version release manager

It's a test repo to get the semantic-release manager into github-actions.

Semantic-release is a nodejs tool and I want to see it working with a non-js language in ci.

## How does it works
- [x] Pull-Requests: enable and configure [github pull-request addon](https://github.com/apps/semantic-pull-requests) for your repo
  - it will check if your commit names are correct for semantic versions
- Attention!
  - The pull-request commit have to be in the semantic version
  - otherwise nothing happens
  - the DEFAULT name is like *"Merge pull request #7 from some/nice/branch"*  
  - for further details see: [semantic-release/commit-analyzer](https://github.com/semantic-release/commit-analyzer/).