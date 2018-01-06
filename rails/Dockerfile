FROM ruby:2.4.1

ENV APP_FOLDER=/app

RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y curl sudo libpq-dev && \
    mkdir ${APP_FOLDER}

WORKDIR ${APP_FOLDER}

CMD ["/bin/bash"]
