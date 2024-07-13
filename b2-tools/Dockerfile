ARG PYTHON_VERSION

FROM python:${PYTHON_VERSION}

RUN pip install b2

ENTRYPOINT [ "ping", "1.1.1.1" ]

VOLUME [ "/backup" ]
