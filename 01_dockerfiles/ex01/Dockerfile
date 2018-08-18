FROM debian

EXPOSE 9987/udp 30033 10011
ENV TS3SERVER_LICENSE accept

RUN apt-get update \
	&& apt-get install wget bzip2 wget ca-certificates -y \
	&& adduser --disabled-password --gecos "" teamspeak

ARG filename=teamspeak3-server_linux_amd64-3.3.0.tar.bz2

WORKDIR /home/teamspeak

RUN wget http://dl.4players.de/ts/releases/3.3.0/$filename \
	&& tar -xvjf $filename

WORKDIR teamspeak3-server_linux_amd64

CMD ["sh", "ts3server_minimal_runscript.sh"]
