ARG MON_AGENT_BASE_VERSION
FROM stackhpc/agent-base

# To force a rebuild, pass --build-arg REBUILD="$(DATE)" when running
# `docker build`
ARG REBUILD=1

# Some issues with the cdn mirror..
RUN sed -i "s/cdn/4/g" /etc/apk/repositories
RUN source ./apk.sh && install_apk_deps
RUN pip install --ignore-installed  git+https://github.com/stackhpc/stackhpc-monasca-agent-plugins.git@master
RUN mv /usr/local/lib/python2.7/site-packages/usr/lib/monasca /usr/lib/monasca

COPY start.sh /
COPY templates/ /templates

CMD ["/start.sh"]
