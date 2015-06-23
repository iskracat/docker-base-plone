Base images of Plone
====================

With this images you can create your own custom plone image.

on a Dockerfile you need to add:

    FROM ramonnb/docker-base-plone:5.0

    COPY custom-buildout.cfg /plone/custom-buildout.cfg
    # Copy all you need on the buildout

    RUN cd /plone && ./bin/buildout -v -c custom-buildout.cfg

    # You can create complex entrypoint shell script
    CMD "./bin/instance fg"
