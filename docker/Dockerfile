FROM ubuntu:latest

RUN apt-get update && apt-get install -y doxygen cmake

COPY test /home/test
WORKDIR /home/test
RUN mkdir build
WORKDIR build
RUN cmake ..
RUN make && make doxygen
