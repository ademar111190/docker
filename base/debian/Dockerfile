FROM debian:stable-20210408

# apt
RUN yes | apt-get update
RUN yes | apt-get dist-upgrade
RUN yes | apt-get upgrade
RUN yes | apt-get install neofetch
RUN yes | apt-get install git

# command
CMD neofetch
