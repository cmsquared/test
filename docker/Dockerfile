FROM ubuntu:latest

RUN apt-get update && apt-get install -y make cmake git gcc g++ doxygen

COPY test /home/test
WORKDIR /home/test
RUN mkdir build
WORKDIR build
RUN cmake .. && make && make doxygen
