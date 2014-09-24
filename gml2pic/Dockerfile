FROM ubuntu:14.04
MAINTAINER j.iwamoto

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y git unzip make gcc wget libtulip-ogdf-4.4
RUN wget https://github.com/ogdf/ogdf/archive/master.zip && unzip master.zip
RUN apt-get install -y g++
RUN apt-get install -y python
RUN sed -i"" -e 's/\/\/archive.ubuntu.com/\/\/ftp.jaist.ac.jp/g' /etc/apt/sources.list
RUN apt-get update && apt-get install -y qt4-default
RUN wget http://www.ogdf.net/lib/exe/fetch.php/tech:ogdf.v2012.07.zip
RUN unzip tech\:ogdf.v2012.07.zip && cd OGDF && ./makeMakefile.sh && make
RUN wget -O gml2pic-v2.0.zip http://www.ogdf.net/lib/exe/fetch.php/project:gml2pic-v2.0.zip?cache=nocache
RUN unzip gml2pic-v2.0.zip
RUN echo "OGDF_INSTALL_PATH = /OGDF" > /gml2pic/gml2pic.config
RUN cd gml2pic && qmake && make

