Below are gitlab-ci examples
```
test_variable:
  stage: test
  script:
    - echo "$CI_JOB_STAGE"
```
