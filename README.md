# Gitlab Docker
```
login user as root and setup password
```

### Gitlab share runner setup
```
$ docker volume create gitlab-share-runner-config
$ docker run -d --name gitlab-share-runner --restart always -v /var/run/docker.sock:/var/run/docker.sock -v gitlab-share-runner-config:/etc/gitlab-runner gitlab/gitlab-runner:latest
$ docker run --rm -it -v gitlab-share-runner-config:/etc/gitlab-runner gitlab/gitlab-runner:latest register
open https://gitlab.suitdev.com/admin/runners
set url & token
Provide the runner executor. For most use cases, enter docker
default image enter php:8.0
```

### Gitlab specific runner setup
```
$ docker run --rm -it -v gitlab-runner-config:/etc/gitlab-runner gitlab/gitlab-runner:latest register
open https://gitlab.suitdev.com/fajar/test/-/settings/ci_cd#js-runners-settings
```
