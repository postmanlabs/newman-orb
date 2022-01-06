# Orb Project Template

<!---
[![CircleCI Build Status](https://circleci.com/gh/postmanlabs/newman-orb.svg?style=shield "CircleCI Build Status")](https://circleci.com/gh/postmanlabs/newman-orb) [![CircleCI Orb Version](https://badges.circleci.com/orbs/postman/newman.svg)](https://circleci.com/orbs/registry/orb/postman/newman) [![GitHub License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://raw.githubusercontent.com/postmanlabs/newman-orb/master/LICENSE) [![CircleCI Community](https://img.shields.io/badge/community-CircleCI%20Discuss-343434.svg)](https://discuss.circleci.com/c/ecosystem/orbs)

--->

CircleCI Orb (postman/newman) for running Postman collections with Newman - https://github.com/postmanlabs/newman

This Orb is available on CircleCI registry as `postman/newman`

## Usage

To use the `postman/newman` Orb, reference it in your CircleCI config and then use the `newman-run` command.

```yaml
version: 2.1
orbs:
  newman: postman/newman@0.0.2
jobs:
  newman-collection-run:
    # use the official newman docker image via newman/postman-newman-docker executor
    executor: newman/postman-newman-docker

    steps:
      # checkout step is optional if you are not referencing any files from the project
      - checkout

      # use newman-run command
      - newman/newman-run:
          collection: ./collection.json
```

**Meta**: This repository is open for contributions! Feel free to open a pull request with your changes. Due to the nature of this repository, it is not built on CircleCI. The Resources and How to Contribute sections relate to an orb created with this template, rather than the template itself.

## Resources

[CircleCI Orb Registry Page](https://circleci.com/orbs/registry/orb/postman/newman-orb) - The official registry page of this orb for all versions, executors, commands, and jobs described.
[CircleCI Orb Docs](https://circleci.com/docs/2.0/orb-intro/#section=configuration) - Docs for using and creating CircleCI Orbs.

### How to Contribute

We welcome [issues](https://github.com/postmanlabs/newman-orb/issues) to and [pull requests](https://github.com/postmanlabs/newman-orb/pulls) against this repository!

### How to Publish

- Create and push a branch with your new features.
- When ready to publish a new production version, create a Pull Request from _feature branch_ to `master`.
- The title of the pull request must contain a special semver tag: `[semver:<segment>]` where `<segment>` is replaced by one of the following values.

| Increment | Description                       |
| --------- | --------------------------------- |
| major     | Issue a 1.0.0 incremented release |
| minor     | Issue a x.1.0 incremented release |
| patch     | Issue a x.x.1 incremented release |
| skip      | Do not issue a release            |

Example: `[semver:major]`

- Squash and merge. Ensure the semver tag is preserved and entered as a part of the commit message.
- On merge, after manual approval, the orb will automatically be published to the Orb Registry.

For further questions/comments about this or other orbs, visit the Orb Category of [CircleCI Discuss](https://discuss.circleci.com/c/orbs).
