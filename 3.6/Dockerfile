FROM inutano/wget:latest AS downloader

RUN wget https://raw.githubusercontent.com/winewei/tools/master/jdk1.8.0_181.tar.gz --no-check-certificate
RUN wget https://raw.githubusercontent.com/winewei/tools/master/apache-maven-3.6.0.tar.gz --no-check-certificate
RUN tar xf jdk1.8.0_181.tar.gz
RUN tar xf apache-maven-3.6.0.tar.gz


FROM debian:stretch-slim

COPY --from=downloader /jdk1.8.0_181 /usr/local/jdk1.8.0_181
COPY --from=downloader /apache-maven-3.6.0 /usr/local/apache-maven-3.6.0

ENV JAVA_HOME=/usr/local/jdk1.8.0_181
ENV JRE_HOME=/usr/local/jdk1.8.0_181/jre
ENV PATH=.:/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/jdk1.8.0_181/bin:/usr/local/apache-maven-3.6.0/bin
