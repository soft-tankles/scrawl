
THRIFT = /usr/local/thrift-0.9.1/bin/thrift

top_dir = ../..

AM_CPPFLAGS =   -I/usr/local/thrift-0.9.1/include \
                -I./gen-cpp

LIBS =  -L/usr/local/thrift-0.9.1/lib -lthrift

gen-cpp/spider_constants.cpp:
	${THRIFT} -r --gen cpp spider.thrift
	${THRIFT} -r --gen py spider.thrift

noinst_LIBRARIES = libspider_webservice.a

libspider_webservice_a_SOURCES = gen-cpp/spider_constants.cpp gen-cpp/spider_types.cpp gen-cpp/SpiderWebService.cpp

noinst_PROGRAMS = client
client_SOURCES = client.cpp
client_LDADD   = libspider_webservice.a

