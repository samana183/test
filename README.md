
https://github.com/tongzh/pact-jvm-minimum-demo


image: maven:latest

variables:
  MAVEN_OPTS: "-Dmaven.repo.local=.m2/repository"

cache:
  paths:
    - .m2/repository/
    - target/


stages:
  - build
  - publish

variables:
  
  TEST_VAR : ""

build:
  stage: build
  script:
    - cd consumer && mvn clean install -DskipTests=false



  artifacts:
    paths:
    -  consumer/target/pacts/*.json 
