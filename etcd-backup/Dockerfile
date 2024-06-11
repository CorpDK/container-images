FROM registry.k8s.io/etcd:3.5.12-0 AS etcdbuilder

FROM python:3.12-alpine3.20

RUN pip install b2

COPY --from=etcdbuilder /usr/local/bin/etcdctl* /usr/local/bin/

VOLUME [ "/etc/kubernetes/pki/etcd" ]
