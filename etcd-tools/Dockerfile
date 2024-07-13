ARG ETCD_VERSION
ARG ALPINE_VERSION

FROM bitnami/etcd:${ETCD_VERSION} AS etcdbuilder

FROM alpine:${ALPINE_VERSION}

COPY --from=etcdbuilder --chown=root:root /opt/bitnami/etcd/bin/etcdctl /opt/bitnami/etcd/bin/etcdutl /usr/local/bin/

ENTRYPOINT [ "ping", "1.1.1.1" ]

VOLUME [ "/etc/kubernetes/pki/etcd", "/backup" ]
