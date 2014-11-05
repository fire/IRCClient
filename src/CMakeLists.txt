set(ircclient_SOURCE IRCClient.cpp IRCClient.h IRCHandler.cpp IRCHandler.h IRCSocket.cpp IRCSocket.h Main.cpp Thread.cpp Thread.h)

add_library(ircclientdll SHARED ${ircclient_SOURCE})
add_executable(ircclient ${ircclient_SOURCE})

if(WIN32)
  target_link_libraries(ircclientdll wsock32 ws2_32)
  target_link_libraries(ircclient wsock32 ws2_32)
endif()
