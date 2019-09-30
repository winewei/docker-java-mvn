FROM inutano/wget:latest AS downloader

RUN wget -q https://raw.githubusercontent.com/winewei/tools/master/apache-maven-3.6.0.tar.gz --no-check-certificate
RUN tar xf apache-maven-3.6.0.tar.gz


FROM pristtlt/java:1.8

COPY --from=downloader /apache-maven-3.6.0 /usr/local/apache-maven-3.6.0

ENV PATH=$PATH:/usr/local/apache-maven-3.6.0/bin
