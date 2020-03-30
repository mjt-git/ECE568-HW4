CC=g++
CFLAGS=   #-pedantic -Werror -Wall #-O3 -fPIC  -lpthread                                 
#CFLAGS=-ggdb3 -fPIC

all: server client

server: main.cpp Client.hpp Server.hpp Socket.hpp
	g++ -std=c++11 -pthread -o server main.cpp

client: client.cpp Client.hpp Server.hpp Socket.hpp
	g++ -std=c++11 -pthread -o client client.cpp

clean:
	rm -rf server client *.o *~


