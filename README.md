# newman-orb
CircleCI Orb (postman/newman) for running Postman collections with Newman - https://github.com/postmanlabs/newman

This Orb is available on CircleCI registry as `postman/newman`

## Usage
To use the `postman/newman` Orb, reference it in your CircleCI config and then use the `newman-run` command.
```
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

## Help & Support
Open a new issue at https://github.com/postmanlabs/newman-orb/issues

## Contributing
#### Publishing a new version

1. Install [CircleCI CLI](https://github.com/CircleCI-Public/circleci-cli/blob/master/README.md#getting-started)

2. Validate orb definition
```
circleci orb validate src/orb.yml
```

3. Publish to CircleCI registry

**NOTE**: You need to be an admin of `postmanlabs` GitHub [org](https://github.com/postmanlabs) to publish new versions of `postman/newman` orb.

```
circleci orb publish src/orb.yml postman/newman@<version>
```