# Copyright (c) 2022 Open Technologies for Integration
# Licensed under the MIT license (see LICENSE for details)

#FROM tdolby/experimental:ace-minimal-11.0.0.11-alpine
ARG BASE_IMAGE=ace-server-prod:12.0.7.0-r3
FROM $BASE_IMAGE

# Used for tekton and Maven containers

LABEL "maintainer"="trevor.dolby@ibm.com"

WORKDIR /tmp/maven-output

RUN mkdir /home/aceuser/ace-server/shared-classes || /bin/true
RUN touch /home/aceuser/ace-server/shared-classes/test.txt
COPY ace-server /tmp/maven-output/ace-server/
RUN rm -rf /home/aceuser/ace-server/run/* || /bin/true
RUN cp -r /tmp/maven-output/ace-server/run/* /home/aceuser/ace-server/run/

