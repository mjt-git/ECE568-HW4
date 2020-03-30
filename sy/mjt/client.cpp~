#include "Server.hpp"
#include "Client.hpp"
#include <vector>
#include <string>
#include <sstream>
#include <iostream>
#include <thread>
#include <sys/types.h>
#include <sys/socket.h>
#include <sys/time.h>
#include <mutex>

using namespace std;

int main(int argc, char * argv[]){
  if(argc!=3){
    cout<<"wrong argument number!"<<endl;
  }
  Client clients;
  clients.build_client(argv[1],argv[2]);
  int socket_fd = clients.get_socket();
  cout<<"please input the delay count & the bucket number:"<<endl;
  string message;
  getline(cin,message);
  send(socket_fd,message.c_str(),message.size(),0);
  int update_val=0;
  recv(socket_fd,&update_val,sizeof(update_val),MSG_WAITALL);
  stringstream ss;
  ss<<"the new value of bucket is "<<update_val;
  cout<<ss.str()<<endl;
  return EXIT_SUCCESS;
}
