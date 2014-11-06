list(APPEND ircclient_SOURCE IRCClient.cpp IRCHandler.cpp IRCSocket.cpp Main.cpp Thread.cpp)

list(APPEND ircclient_HEADERS ../include/IRCClient.h ../include/IRCHandler.h ../include/IRCSocket.h ../include/Thread.h)

add_library(ircclientdll SHARED ${ircclient_SOURCE} ${ircclient_HEADERS})
add_executable(ircclient ${ircclient_SOURCE} ${ircclient_HEADERS})

if(WIN32)
  target_link_libraries(ircclientdll wsock32 ws2_32)
  target_link_libraries(ircclient wsock32 ws2_32)
endif()
