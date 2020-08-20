# Gitlab



### Configure gitlab runner



````bash
 $ docker exec -it glr /bin/bash
 $ gitlab-runner register
````



The following information can be found [here](https://docs.gitlab.com/runner/register/index.html). Be careful what you type in, backspace, home, delete and arrows keys don't work. They give weird characters then you have to control+c and start again.



````bash
Please enter the gitlab-ci coordinator URL (e.g. https://gitlab.com )
https://gitlab.com
$ https://gitlab.cardstrip.com
````



````bash
Please enter the gitlab-ci token for this runner
$ xxxxxxxx
````



Now get You can get the token from [here](https://gitlab.cardstrip.com/cardstrip/app/settings/ci_cd) under the expanded `Runner settings` section. Use the registration token as specified at point 3.



```bash
Please enter the gitlab-ci description for this runner:
$ Node application runner
```



````bash
Please enter the gitlab-ci tags for this runner (comma separated):
$ node,ng,nest
````



````bash
Please enter the executor: ssh, docker+machine, docker-ssh+machine, kubernetes, docker, parallels, virtualbox, docker-ssh, shell:
$ docker
````

````bash
Please enter the Docker image (eg. ruby:2.1):
$ node:latest
````



#### Runners in privileged mode

Make sure that the docker container of the runner is started with --privileged. If not you can always configure it in file `/var/network/gitlab-runner/config.toml` of the runner:

````yaml
[[runners]]
  name = "Node, ng, nest"
  url = "https://gitlab.cardstrip.com/"
  token = "xxxxxxxx"
  executor = "docker"
  [runners.docker]
    tls_verify = true
    image = "node:latest"
    privileged = true
    disable_cache = false
    volumes = ["/cache"]
    shm_size = 0
  [runners.cache]
````

