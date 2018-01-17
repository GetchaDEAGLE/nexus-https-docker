FROM sonatype/nexus3:3.7.1
LABEL maintainer="Daniel Eagle"

# switch to root so as to have proper permissions
USER root

# Add Tini
ENV TINI_VERSION v0.16.1
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN chmod +x /tini

# expose additional ports for Docker registry
EXPOSE 5000 5001

# Switch back to nexus user
USER nexus

ENTRYPOINT ["/tini", "--"]

CMD ["sh", "-c", "${SONATYPE_DIR}/start-nexus-repository-manager.sh"]