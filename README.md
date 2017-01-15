# Commentator
A simple pull-request comentator for travis.

![alt](image.png)

## Usage

1. add commentator as a dev dependency
    ```bash
    npm i commentator --save-dev
    ```
2. Edit your `travis.yml` with the message you'd like to comment your PR with.
    ```yml
    language: node_js
    cache:
      directories:
        - node_modules
    notifications:
      email: false
    node_js:
      - '7'
    before_script:
      - npm prune
      - npm run coverage | commentator
    after_success:
      - npm run semantic-release
    branches:
      except:
        - /^v\d+\.\d+\.\d+$/
    ```
