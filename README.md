# Commentator

[![Greenkeeper badge](https://badges.greenkeeper.io/tusharmath/commentator.svg)](https://greenkeeper.io/)
A simple pull-request (PR) comentator for travis.

## Usage

Edit your `travis.yml` with the message you'd like to comment your PR with.

```diff
    language: node_js
    cache:
      directories:
        - node_modules
    notifications:
      email: false
    node_js:
      - '7'
    before_install:
+     - npm i -g commentator
    before_script:
      - npm prune
+     - npm run coverage | commentator
    after_success:
      - npm run semantic-release
    branches:
      except:
        - /^v\d+\.\d+\.\d+$/
```

Everytime now when travis runs the above `npm run coverage` script it will comment the results on the PR.
