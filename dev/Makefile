DOCKER_APP = containers-app
DOCKER_GIT = unicity/containers
DOCKER_PORT = 49833

# make rebuild-docker
rebuild-docker:
	docker build -t $(DOCKER_GIT) .

# make run-docker
run-docker: rebuild-docker clean-docker
	docker run -d -p $(DOCKER_PORT):80 --name="$(DOCKER_APP)" \
	-v $$PWD/src/html:/var/www/Containers/html \
	$(DOCKER_GIT) /bin/bash -c "(rm -f /var/run/httpd/httpd.pid || true) && /usr/sbin/httpd -DFOREGROUND"

# make qa-restart-docker
qa-restart-docker:
	sudo service docker restart; sleep 10; docker --version

# make clean-docker
clean-docker:
	-docker stop $(DOCKER_APP)
	-docker rm -f $(DOCKER_APP)
