FROM debian
ENV TS3SERVER_LICENSE=accept
WORKDIR /home/teamspeak
EXPOSE 9987/udp 10011 30033
RUN apt-get update
RUN apt-get upgrade -y 
RUN apt-get install -y wget bzip2
RUN wget http://dl.4players.de/ts/releases/3.6.0/teamspeak3-server_linux_amd64-3.6.0.tar.bz2
RUN tar -xvf teamspeak3-server_linux_amd64-3.6.0.tar.bz2
WORKDIR teamspeak3-server_linux_amd64
ENTRYPOINT cat -e doc/privilegekey_guide.txt && sh ts3server_minimal_runscript.sh

# docker build -t image01 .
# docker run --rm -it -p 9987:9987/udp -p 10011:10011 -p 30033:30033 image01
# TS3SERVER_LICENSE=accept accept the license agreement https://docs.docker.com/samples/library/teamspeak/
# 9987/udp 10011 30033 - TeamSpeak 3 server default ports https://www.speedguide.net/port.php?port=9987
# check version of teamspeak, for example 3.6.0 if works good, but 3.0.13.4 is not, because you cant
# connect to the server in new version of client.