CC = g++ -O
CPPFLAGS = -std=c++11 -I. -I/System/Library/Frameworks/OpenCL.framework/Headers/
LDFLAGS = -L/System/Library/Frameworks/OpenCL.framework/Libraries/

SRCS = Core/CommonData.cpp Core/Farm.cpp Core/Log.cpp Core/Miner.cpp Core/MinerManager.cpp Core/Worker.cpp \
       Hash/sha256.cpp Hash/sha256_mod.cpp MinerEngine/CLMiner.cpp MinerEngine/XCpuMiner.cpp \
       Utils/CpuInfo.cpp Utils/PathUtils.cpp Utils/Random.cpp Utils/Utils.cpp \
       XDagCore/XAddress.cpp XDagCore/XHash.cpp XDagCore/XNetwork.cpp XDagCore/XBlock.cpp \
       XDagCore/XPool.cpp XDagCore/XTaskProcessor.cpp XDagCore/XTaskWrapper.cpp \
       XDagCore/dar/crc_c.cpp 	 XDagCore/dfstools/dfslib_crypt.cpp XDagCore/dfstools/dfslib_string.cpp


OBJS = $(SRCS:.cpp=.o)

%.o: %.cpp
	$(CC) -c $(CFLAGS) $(CPPFLAGS) $(INCLUDES) $< -o $@

xdag-gpu: main.o $(OBJS)
	$(CC) -o xdag-gpu $(LDFLAGS) main.o $(OBJS) -framework OpenCL -lpthread -lboost_system

all: xdag-gpu
