FROM ubuntu:trusty

RUN apt-get -y update && apt-get install -y build-essential curl && apt-get clean

RUN cd /tmp && curl -LO http://www.cpan.org/src/5.0/perl-5.16.3.tar.gz
RUN cd /tmp && tar xvzf perl-5.16.3.tar.gz
RUN cd /tmp/perl-5.16.3 && ./Configure -des && make && make install
RUN cd /tmp && rm -rf perl-5.16.3.tar.gz perl-5.16.3

RUN curl -L https://cpanmin.us | perl - --sudo App::cpanminus

CMD perl -V && cpanm -V
