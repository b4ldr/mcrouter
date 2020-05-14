FROM            debian:buster

MAINTAINER      mcrouter <mcrouter@fb.com>

ENV             MCROUTER_DIR            /usr/local/mcrouter
ENV             MCROUTER_REPO           https://github.com/b4ldr/mcrouter.git
ENV             MCROUTER_BRANCH         docker_buster
ENV             DEBIAN_FRONTEND         noninteractive

RUN             apt-get update && apt-get install -y git && \
                mkdir -p $MCROUTER_DIR/repo && \
                cd $MCROUTER_DIR/repo && git clone $MCROUTER_REPO && \
                git checkout $MCROUTER_BRANCH && \
                cd $MCROUTER_DIR/repo/mcrouter/mcrouter/scripts && \
                ./install_debian_buster.sh $MCROUTER_DIR && \
                ./clean_debian_buster.sh $MCROUTER_DIR && rm -rf $MCROUTER_DIR/repo && \
                ln -s $MCROUTER_DIR/install/bin/mcrouter /usr/local/bin/mcrouter

ENV             DEBIAN_FRONTEND newt
