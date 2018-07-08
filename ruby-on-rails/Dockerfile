FROM ubuntu:latest
RUN apt-get update -y
RUN apt-get install -y build-essential libgmp3-dev patch ruby-dev zlib1g-dev postgresql-client libpq5 libpq-dev
COPY . /app
WORKDIR /app
RUN pip3 install -r requirements.txt

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6
RUN echo "deb [ arch=amd64 ] http://repo.mongodb.org/apt/ubuntu/ xenial/mongodb-org/3.4 multiverse" |  tee /etc/apt/sources.list.d/mongodb-3.4.list
RUN apt-get update && apt-get install -y mongodb-org
RUN apt-get install -y redis-server
RUN apt-get update && apt-get install -y git

RUN apt-get install -y ruby
RUN apt-get install -y openssl curl

RUN apt-get install -y software-properties-common
RUN apt-add-repository -y ppa:rael-gc/rvm
RUN apt-get update
RUN apt-get install -y rvm
RUN gem install bundler
