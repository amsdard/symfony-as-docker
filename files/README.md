{name}
========================
* [local] {name}.test
* [dev] {name}.test.amsdard.io
* [live] 

Requirements
---
 * configure Your local [projects enrironment](https://bitbucket.org/as-docker/projects-environment)
 * make sure You have [YAKE](https://yake.amsdard.io/) installed


Run project
---
```
yake configure
yake up
```
* run `yake encore dev --watch` (or `yake npm run watch`) in background to work with assets
* make sure `{name}.test` domain is routed to Your localhost


Additional info
---
* do not use `require-dev` in composer.json (keep common vendors)


Deploy (dev / rancher)
---
```
yake deploy php
yake deploy nginx
```
* import `./deploy/rancher/docker-compose.yml` into Rancher + complete ENVs
* make sure `mysql` works on specific host (Scheduling)
* make sure `nginx` has *Health Check* enabled


Deploy (prod)
---
```
yake deploy php
yake deploy nginx
```
* import `./deploy/prod/docker-compose.yml` into server + copy ENV files from `docker` directory
* `docker-compose pull --parallel --quiet`
* `docker-compose up -d --force-recreate`

