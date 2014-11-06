set(ircclient_SOURCE IRCClient.cpp IRCHandler.cpp IRCSocket.cpp Main.cpp Thread.cpp )

add_library(ircclientdll SHARED ${ircclient_SOURCE})
add_executable(ircclient ${ircclient_SOURCE})

include_directories(../include)
if(WIN32)
  target_link_libraries(ircclientdll wsock32 ws2_32)
  target_link_libraries(ircclient wsock32 ws2_32)
endif()
