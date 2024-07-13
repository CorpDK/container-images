ARG ETCD_VERSION
ARG ALPINE_VERSION

FROM bitnami/etcd:${ETCD_VERSION} AS etcdbuilder

FROM alpine:${ALPINE_VERSION}

COPY --from=etcdbuilder --chown=root:root /opt/bitnami/etcd/bin/etcdctl /opt/bitnami/etcd/bin/etcdutl /usr/local/bin/

ENV ETCDCTL_API=3
ENV ETCDCTL_CACERT="/etc/kubernetes/pki/etcd/ca.crt"
ENV ETCDCTL_CERT="/etc/kubernetes/pki/etcd/client.crt"
ENV ETCDCTL_KEY="/etc/kubernetes/pki/etcd/client.key"

ENTRYPOINT [ "ping", "1.1.1.1" ]

VOLUME [ "/etc/kubernetes/pki/etcd", "/backup" ]
