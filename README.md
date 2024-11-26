Be sure to have OpenSSL library installed. If you run this project on Hopper, you don't need to install anything.
You only need to write code in the common.cpp file under the Common folder (encryptMessage and decryptMessage methods)

To run the chat application:
1. In the project3_part1 directory, run the following commands:
   + mkdir build
   + cd build
   + cmake ..
   + make
2. Run the client and server (you can have multiple client instances):
+ In the build directory, run the server by: (run the server first)
  + cd Server
  + ./server_executable
+ Open another terminal, in the build directory, run the client by:
  + cd Client
  + ./client_executable
   
Testing:
In the client terminal, type a message
In the server terminal, an encrypted message and the message you just typed in the client terminal will show up
If both messages match, then you do encryption and decryption methods correctly

This project was worked on by Pascal Sikorski and Gustavo Lucca. There was a change in CMakeLists.txt of line:

cmake_minimum_required(VERSION 3.27)
to
cmake_minimum_required(VERSION 3.26.5)

In Server/server.cpp, there was an error at line:

send(clientSocket, decryptedBuffer,  strlen(reinterpret_cast<const char*>(decryptedBuffer)), 0);

We added import:
#include <string>

and the unknown function error went away.

In total, making the correct common.cpp and addressing the other problems of the repo led to us having a working output.
