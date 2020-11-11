stages:
  - build
  - test
  - deploy

variables:
  
  TEST_VAR : ""

build:
  stage: build
  script:
    - echo "Building .."


test:
  stage: test
  script: # TODO: write a test script
    - echo "Testing  .."
  dependencies:
    - build

deploy_dev:
  stage: deploy
  environment:
    name: Dev
  script:

    - echo "test" > pact.json
   
  artifacts:
    paths:
    -  pact.json 
