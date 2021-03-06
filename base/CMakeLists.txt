set(SOURCES
    BigInteger.cpp
    BigInteger.hpp
    cl2.hpp
    CommandLineReader.hpp
    Convertors.cpp
    Convertors.hpp
    Dynamic.cpp
    Dynamic.hpp
    Endian.hpp
    Event.hpp
    InfoProvider.cpp
    InfoProvider.hpp
    json.cpp
    json.hpp
    Logging.cpp
    Logging.hpp
    Manageable.cpp
    Manageable.hpp
    Reference.hpp
    SecureTcpClientSocket.cpp
    SecureTcpClientSocket.hpp
    Semaphore.hpp
    SHA256.cpp
    SHA256.hpp
    Signal.hpp
    StringUtils.cpp
    StringUtils.hpp
    tinyxml2.cpp
    tinyxml2.hpp
    url.cpp
    url.hpp
    Utils.cpp
    Utils.hpp
    WaitableTimer.hpp
    wraphelper.h
    TcpClientSocket.cpp
    TcpClientSocket.hpp
    TcpAsyncClientSocket.cpp
    TcpAsyncClientSocket.hpp
    TcpServerSocket.cpp
    TcpServerSocket.hpp
)

if (EQUIHASHCL)
    set(SOURCES
        ${SOURCES}
        AdlInfoProvider.cpp
        AdlInfoProvider.hpp
        AmdSysFsInfoProvider.cpp
        AmdSysFsInfoProvider.hpp
    )
endif()

if (EQUIHASHCUDA)
    set(SOURCES
        ${SOURCES}
        NvidiaInfoProvider.cpp
        NvidiaInfoProvider.hpp
    )
endif()

add_library(base STATIC ${SOURCES})
target_link_libraries(base PRIVATE ${OPENSSL_LIBSSL} ${OPENSSL_LIBCRYPTO})
target_include_directories(base PRIVATE ..)

