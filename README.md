# Container.lib

Assumption: The Dockerfile contains no sensitive information.

### Making DockerHub Repository:

1. Create org in Docker hub (`unicityintl`).
2. Created `php56httpd` repository.

### Building Image:

1. Build image: `docker build -f Dockerfile.php56httpd -t unicityintl/php56httpd .`

Or

1. Build image: `docker build -f Dockerfile.php56httpd .`
2. Verified the image hash of the newly built image: `docker images`
3. Tag image: `docker tag IMAGE_HASH unicityintl/php56httpd:latest`

### Committing Image:

1. `docker login --username=YOUR_USERNAME`
2. Type in your Docker Hub password.
3. `docker push unicityintl/php56httpd`

See also, https://ropenscilabs.github.io/r-docker-tutorial/04-Dockerhub.html.

### Using Image:

1. Modify the Dockerfile to start with `FROM unicityintl/php56httpd:latest`.

See also, https://github.com/Unicity/Hydra.php/issues/873
