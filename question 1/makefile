CC = clang++ -std=c++11 -stdlib=libc++
CFLAGS = -g -Wall
OBJECT_DIR = obj
SOURCE_DIR = src

.PHONY: default all clean

default: maze
all: default

HEADERS = $(wildcard $(SOURCE_DIR)/*.hpp)

GENERATE_OBJECTS = $(OBJECT_DIR)/main.o $(OBJECT_DIR)/maze.o $(OBJECT_DIR)/point.o

$(OBJECT_DIR)/%.o: $(SOURCE_DIR)/%.cpp $(HEADERS)
	$(CC) $(CFLAGS) -c $< -o $@

.PRECIOUS: $(TARGET) $(OBJECTS)

maze: $(GENERATE_OBJECTS)
	$(CC) $(CFLAGS) $(GENERATE_OBJECTS) -o $@

clean:
	-rm -f $(OBJECT_DIR)/*.o
	-rm -f maze
