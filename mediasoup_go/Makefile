TEMPLATE_NAME ?= registry.cn-hangzhou.aliyuncs.com/frank_dev/mediasoup-app:0.0.1

# basepath=$(cd `dirname $0`; pwd)
# pes_parent_dir:=$(shell pwd)/$(lastword $(MAKEFILE_LIST))
# pes_parent_dir:=$(shell dirname $(pes_parent_dir))

build:
	@docker build -t $(TEMPLATE_NAME) .

push:
	@docker push $(TEMPLATE_NAME)

run:
	@docker run --rm --name="mediasoup-app"  -itd $(TEMPLATE_NAME) 