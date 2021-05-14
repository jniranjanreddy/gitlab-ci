Below are gitlab-ci examples
```
test_variable:
  stage: test
  script:
    - echo "$CI_JOB_STAGE"
```
```
stages: 
  - build
  - test

build the car:
  stage: build
  script:
    - mkdir build
    - cd build
    - touch car.txt
    - echo "Chassisss" >> car.txt
    - echo "engine" >> car.txt
    - echo "Wheels" >> car.txt
  artifacts: 
    paths: 
      - build/

test the car:
  stage: test
  script:
    - test -f build/car.txt
    - cd build
    - grep "Chassis" car.txt
    - grep "engine" car.txt

```
