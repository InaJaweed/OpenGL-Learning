
# Compiler and flags
CC = gcc
CFLAGS = -Wall -Wextra -std=c99 -Iinclude -I/opt/homebrew/Cellar/glfw/3.4/include -DGL_SILENCE_DEPRECATION
LDFLAGS = -L/opt/homebrew/Cellar/glfw/3.4/lib -lglfw -framework OpenGL

# Directories
SRC_DIR = src
INCLUDE_DIR = include
BUILD_DIR = build

# Target executable
TARGET = opengl_app

# Source files and objects
SRCS = $(wildcard $(SRC_DIR)/*.c)
OBJS = $(patsubst $(SRC_DIR)/%.c, $(BUILD_DIR)/%.o, $(SRCS))

# Rules
all: $(TARGET)

$(TARGET): $(OBJS)
	@echo "Linking $(TARGET)..."
	$(CC) -o $@ $^ $(LDFLAGS)

$(BUILD_DIR)/%.o: $(SRC_DIR)/%.c | $(BUILD_DIR)
	@echo "Compiling $<..."
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c $< -o $@

$(BUILD_DIR):
	@mkdir -p $@

clean:
	@echo "Cleaning up..."
	@rm -rf $(BUILD_DIR) $(TARGET)

.PHONY: all clean
