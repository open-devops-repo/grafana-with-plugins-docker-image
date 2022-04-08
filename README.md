grafana-with-plugins-docker-image
=================================

Introduction
------------
This projects builds a Docker image with [crane](https://github.com/google/go-containerregistry/tree/main/cmd/crane) with pre-installed plugins. It's based on [Build with Grafana Image Renderer plugin pre-installed](https://grafana.com/docs/grafana/latest/installation/docker/#build-with-grafana-image-renderer-plugin-pre-installed) and [ubuntu.Dockerfile](https://github.com/grafana/grafana/blob/main/packaging/docker/custom/ubuntu.Dockerfile)
and publishes the result on Dockerhub under ```opendevopsrepo/grafana-with-plugins:latest```.



How to fork this repo and its automatic CI builds
-------------------------------------------------
* have a GitHub.com and a hub.docker.com account ready
* fork this git repo into your own GitHub.com repo
* create an hub.docker.com access token (https://hub.docker.com/settings/security)
* set this hub.docker.com access token in your GitHub.com repo Settings/Security/Secrets/Actions (https://github.com/your-GitHub.com-username/your-GitHub.com-repo-name/settings/secrets/actions)
    * set DOCKERHUB_USERNAME={your hub.docker.com user name}
    * set DOCKERHUB_TOKEN={your hub.docker.com access token from above}
* in .github/workflows/github-actions.yml replace tag "opendevopsrepo/jenkins-plugins-collection" with "{your hub.docker.com username}/{your new hub.docker.com repo name}"
* set a Readme text on hub.docker.com (https://hub.docker.com/repository/docker/your-hub.docker.com-username/your-new-hub.docker.com-repo-name/general)

After this setup, every push to "main" branch in your GitHub.com repo should trigger a CI build that uploads the docker image to your hub.docker.com repo.

