FROM ubuntu:16.04

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y ca-certificates openssh-server wget postfix

RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && chmod 777 script.deb.sh && ./script.deb.sh && apt-get install -y gitlab-ce

RUN apt update && apt install -y tzdata && \
  apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

# https://gitlab.com/gitlab-org/omnibus-gitlab/issues/2229
# https://gitlab.com/gitlab-org/omnibus-gitlab/issues/430
# without "tail -f /dev/null"  your GitLab will shut down
# Check
# docker build -t image03 .
# docker run -it --rm -p 8080:80 -p 8022:22 -p 8443:443 --privileged image03