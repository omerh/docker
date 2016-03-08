FROM ubuntu:14.04

# prerequists
RUN apt-get update --fix-missing && apt-get install -y git build-essential libreadline-dev zlib1g-dev libffi-dev libpq-dev libsqlite3-dev wget curl

# rbenv
RUN cd /usr/local \
	&& git clone https://github.com/sstephenson/rbenv.git rbenv  \
	&& cd /usr/local/rbenv \
	&& mkdir plugins && cd plugins \
	&& git clone https://github.com/sstephenson/ruby-build.git

ENV PATH /usr/local/rbenv/bin:$PATH

RUN /usr/local/rbenv/plugins/ruby-build/install.sh
RUN echo 'eval "$(rbenv init -)"' >> /etc/profile \
  && echo 'eval "$(rbenv init -)"' >> ~/.bashrc

#Now you have rbenv setup for install (rbenv install 2.1.0)
