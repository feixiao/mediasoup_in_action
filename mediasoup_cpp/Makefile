TEMPLATE_NAME ?= registry.cn-hangzhou.aliyuncs.com/frank_dev/mediasoup-worker:3.7.2

# basepath=$(cd `dirname $0`; pwd)
# pes_parent_dir:=$(shell pwd)/$(lastword $(MAKEFILE_LIST))
# pes_parent_dir:=$(shell dirname $(pes_parent_dir))

build:
	@docker build -t $(TEMPLATE_NAME) .

push:
	@docker push $(TEMPLATE_NAME)