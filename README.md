# Commentator
A simple pull-request comentator for travis.

![alt](image.png)

## Usage

1. Add commentator as a dev dependency
    
    ```bash
    npm i commentator --save-dev
    ```
    
2. Edit your `travis.yml` with the message you'd like to comment your PR with.

    ```diff
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
   + - npm run coverage | commentator
    after_success:
      - npm run semantic-release
    branches:
      except:
        - /^v\d+\.\d+\.\d+$/
    ```
    
   3. That's all! Everytime now when travis runs the above `npm run coverage` script it will comment the results on the PR.
