CONTAINER_NAME = ansible_avd
ANSIBLE_VERSION = 2.9.2
CONTAINER = $(CONTAINER_NAME):$(ANSIBLE_VERSION)
HOME_DIR = $(shell pwd)
UID = $(shell id -u)
GID = $(shell id -g)

.PHONY: all
all:
	#docker build --no-cache -t $(CONTAINER) .
	docker build -f ./docker/$(PLATFORM)/Dockerfile -t $(CONTAINER) . --build-arg UID=$(UID) --build-arg GID=$(GID) --build-arg ANSIBLE=$(ANSIBLE_VERSION)
	docker run -t -d --name $(CONTAINER_NAME)_$(ANSIBLE_VERSION)_$(PLATFORM) -v $(HOME_DIR)/:/git_projects -v /etc/hosts:/etc/hosts $(CONTAINER)
	docker exec -it $(CONTAINER_NAME)_$(ANSIBLE_VERSION)_$(PLATFORM)  /bin/bash

.PHONY: clean
clean:
	docker stop $(CONTAINER_NAME)_$(ANSIBLE_VERSION)_$(PLATFORM)
	docker rm $(CONTAINER_NAME)_$(ANSIBLE_VERSION)_$(PLATFORM)