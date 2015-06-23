FROM python:2.7

ENV PLONE_VERSION 5.0

RUN rm -rf /plone/* \
    && mkdir /plone \
    && git clone https://github.com/plone/buildout.coredev.git -b $PLONE_VERSION /plone \
    && cd /plone \
    && python bootstrap.py \
    && ./bin/buildout -v \
    && chmod -R www-data /plone/var \
    && echo "" >> /plone/parts/instance/etc/zope.conf \
    && echo "effective-user www-data" >> /plone/parts/instance/etc/zope.conf

VOLUME /plone/var/

# Expose
EXPOSE  8080

CMD ["su www-data /plone/bin/instance fg"]