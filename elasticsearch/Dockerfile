ARG ELK_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELK_VERSION}

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu
# RUN elasticsearch-plugin install https://github.com/javacafe-project/elasticsearch-plugin/releases/download/v7.0.0/javacafe-analyzer-7.0.0.zip
# sudo ES_JAVA_OPTS="-Djavax.net.ssl.trustStore=/path/to/trustStore.jks" bin/elasticsearch-plugin install https://host/plugin.zip
RUN elasticsearch-plugin install analysis-nori
RUN elasticsearch-plugin list

USER root
RUN ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime


