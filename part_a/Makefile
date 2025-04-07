CC = g++
CFLAGS = -std=c++17 -Wall -Wextra -O3 -I./src
SRC_DIR = src
BUILD_DIR = build
EXEC = blinkdb

# Explicitly list source files (no wildcards)
SRCS = $(SRC_DIR)/storage_engine.cpp $(SRC_DIR)/repl.cpp
OBJS = $(patsubst $(SRC_DIR)/%.cpp,$(BUILD_DIR)/%.o,$(SRCS))

all: $(BUILD_DIR) $(EXEC)

$(EXEC): $(OBJS)
	$(CC) $(CFLAGS) $^ -o $@

$(BUILD_DIR)/%.o: $(SRC_DIR)/%.cpp | $(BUILD_DIR)
	$(CC) $(CFLAGS) -c $< -o $@

$(BUILD_DIR):
	mkdir -p $(BUILD_DIR)

clean:
	rm -rf $(BUILD_DIR) $(EXEC)

.PHONY: all clean
