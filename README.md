# Deploy CI/CD stack in five minutes on localhost

## Caution
Work in progress, all notes below only for internal use.

## How to configure gitlab/jenkins integration for multibranch pipelines:
  - gitlab: create dedicated user for integration;
  - jenkins: add ssh privite key for gitlab integration;
  - gitlab: generate api token (all scope<sup>*</sup>) and add public ssh key for user above;
  - jenkins: install 'GitLab Branch Source' plugin;
  - jenkins: create gitlab token credentials;
  - jenkins: add gitlab server into jenkins configuration;
  - jenkins: create multibranch pipeline job<sup>**</sup> and configure gitlab source.

\* It's not clear which scope required for push builds results and create webhooks; \
\** Doesn't work actually (?), but "Gitlab Group" project works as expected.

## References
- [How to configure "GitLab Branch Source" plugin](https://jenkins.io/blog/2019/08/23/introducing-gitlab-branch-source-plugin/);
- [Gitlab Dockerfile (source)](https://gitlab.com/gitlab-org/omnibus-gitlab/-/tree/master/docker).
