API_NODE_PATH:=../../web-application/client-react/
DOCKERHUB_REPO:=rustx2802/docker-guru-client-react-nginx

N?=0
.PHONY: build-N
build-N:
	docker build --file ./Dockerfile.${N} \
		-t client-react:${N} \
		-t ${DOCKERHUB_REPO}:${N} \
		${API_NODE_PATH}

.PHONY: build-all
build-all:
	for number in 0 1 2 3 4 5; do \
			N=$$number $(MAKE) build-N; \
	done

.PHONY: push-N
push-N:
	docker push ${DOCKERHUB_REPO}:${N}

.PHONY: push-all
push-all:
	for number in 0 1 2 3 4 5; do \
			N=$$number $(MAKE) push-N; \
	done