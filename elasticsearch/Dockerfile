ARG ELK_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELK_VERSION}

# 패스워드 변경해보자.
RUN echo "elkttukttak" | bin/elasticsearch-keystore add -xf bootstrap.password

# copy custom plugin
ARG PLUGIN_FILE=plugin/*.zip
# plugin/처럼 /로 끝나면 해당 폴더 생성 기대
COPY ${PLUGIN_FILE} /usr/share/elasticsearch/plugin/

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu
RUN elasticsearch-plugin install file:///usr/share/elasticsearch/plugin/javacafe-analyzer-7.9.1.zip

# https 잘안되면 밑의 방식 사용
# sudo ES_JAVA_OPTS="-Djavax.net.ssl.trustStore=/path/to/trustStore.jks" bin/elasticsearch-plugin install https://host/plugin.zip
RUN elasticsearch-plugin install analysis-nori
RUN elasticsearch-plugin list

USER root
RUN ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime