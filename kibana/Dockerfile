ARG ELK_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/kibana/kibana:${ELK_VERSION}

# Add your kibana plugins setup here
# Example: RUN kibana-plugin install <name|url>

USER root
RUN ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime

USER kibana

