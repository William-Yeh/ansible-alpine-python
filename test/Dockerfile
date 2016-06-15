# Dockerfile for building image that contains software stack provisioned by Ansible.
#
# USAGE:
#   $ docker build .
#
# Version  1.0
#


# pull base image
FROM williamyeh/ansible:alpine3-onbuild

MAINTAINER William Yeh <william.pjyeh@gmail.com>


#
# build phase
#

RUN apk --update add sudo

ENV PLAYBOOK test.yml
RUN ansible-playbook-wrapper --extra-vars "alpine_python_3_enabled=true"



#
# test phase
#

CMD ["python3", "--version"]
