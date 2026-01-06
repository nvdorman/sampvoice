OUTPUT_FILE = "sampvoice.so"

COMMON_FLAGS = -m32 -O3 -Ofast -w -fpermissive -fPIC
COMPILE_FLAGS = $(COMMON_FLAGS) -c -idirafter "include"
PRELINK_FLAGS = $(COMMON_FLAGS) -shared -static-libstdc++ -static-libgcc

all:
	g++ $(COMPILE_FLAGS) -std=c++11 include/pawn/*.cpp
	g++ $(COMPILE_FLAGS) -std=c++11 include/raknet/*.cpp
	g++ $(COMPILE_FLAGS) -std=c++17 include/util/*.cpp
	g++ $(COMPILE_FLAGS) -std=c++11 include/ysf/*.cpp
	g++ $(COMPILE_FLAGS) -std=c++17 *.cpp
	g++ $(PRELINK_FLAGS) -o $(OUTPUT_FILE) *.o
	strip -s $(OUTPUT_FILE)
	rm -f *.o

clean:
	rm -f *.o $(OUTPUT_FILE)
