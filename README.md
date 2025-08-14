# Домашнее задание к занятию "`GitLab`" - `Белолипецкий Леонид`


---

### Задание 1

![img](https://github.com/forzetofficial/gitlab-hw/blob/main/img/img1.png)

![img](https://github.com/forzetofficial/gitlab-hw/blob/main/img/img2.png)

![img](https://github.com/forzetofficial/gitlab-hw/blob/main/img/img3.png)

![img](https://github.com/forzetofficial/gitlab-hw/blob/main/img/img4.png)


---

### Задание 2

```yml
stages:
  - test
  - build

test:
  stage: test
  image: golang:1.17
  script:
    - go test .
  tags:
    - linux

build:
  stage: build
  image: docker:latest
  variables:
    DOCKER_HOST: tcp://docker:2375
    DOCKER_TLS_CERTDIR: ""
  services:
    - name: docker:dind
      alias: docker
  before_script:
    - docker info
  script:
    - docker build .
  tags:
    - linux
```

![img](https://github.com/forzetofficial/gitlab-hw/blob/main/img/last.png)


---

