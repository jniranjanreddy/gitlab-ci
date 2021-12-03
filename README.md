Below are gitlab-ci examples

```
How to install gitlab.
 curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
 yum -y install gitlab-ce


```

```
Stage - Keyword is used in a job to define which stage that job is part of.
Stages - Define the order of execution of jobs or group of jobs.

There are 5 default stages:-
 1. .pre
 2. build
 3. test
 4. deploy
 5 .post

```
```
build-job:
  script: 
    - echo "This is from Build Job"
    
test-job:
  script: 
    - echo "This is from test-Job"
    
deploy-job:
  script: 
    - echo "This is from deploy-Job"
```

```
//Single Stage: 

test_variable:
  stage: test
  script:
    - echo "$CI_JOB_STAGE"
```
```
#Double stage or multistage
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
