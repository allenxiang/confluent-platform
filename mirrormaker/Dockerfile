# Builds a docker image for Kafka MirrorMaker.

FROM cgswong/confluent-platform:2.0.1

ENV MM_CFGDIR "/etc/kafka-mirrormaker"
ENV JMX_PORT 7023

COPY mirrormaker-docker.sh /usr/local/bin/
COPY tools-log4j.properties ${SR_CFGDIR}/

RUN mkdir -p ${MM_CFGDIR} &&\
    chmod +x /usr/local/bin/mirrormaker-docker.sh


VOLUME [ "${MM_CFGDIR}" ]
# Expose JMX
EXPOSE ${JMX_PORT}

ENTRYPOINT [ "/usr/local/bin/mirrormaker-docker.sh" ]

