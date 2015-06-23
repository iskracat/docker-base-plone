FROM python:2.7

ENV PLONE_VERSION 4.3

RUN rm -rf /plone/* && mkdir /plone && git clone https://github.com/plone/buildout.coredev.git -b $PLONE_VERSION /plone && cd /plone && python bootstrap.py && ./bin/buildout -v

VOLUME /plone/var/

# Expose
EXPOSE  8080

CMD ["/plone/bin/instance fg"]