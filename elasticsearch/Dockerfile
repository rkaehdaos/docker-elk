ARG ELK_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELK_VERSION}

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu
RUN wget https://github.com/javacafe-project/elastic-book-etc/raw/master/plugin/javacafe-analyzer-6.4.3.zip
RUN elasticsearch-plugin install file:///usr/share/elasticsearch/plugin/javacafe-analyzer-6.4.3.zip
RUN elasticsearch-plugin install analysis-nori
RUN elasticsearch-plugin list

USER root
RUN ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime


