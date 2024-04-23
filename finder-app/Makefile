# Compiler settings
CC := gcc
#CROSS_COMPILE := aarch64-linux-gnu-  # Cross-compiler prefix (adjust as needed)

CFLAGS := -Wall -Wextra  #-O2

# Source files and output binary
SRCS := *.c
OBJS := $(SRCS:.c=.o)
TARGET := writer.exe

# Native build target
.PHONY: 
native: $(TARGET)

# Build rule for native compilation
$(TARGET): $(OBJS)
	$(CC) $(CFLAGS) -o $@ $^

# Build rule for cross-compilation
$(OBJS): %.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

# Clean target
.PHONY: clean
clean:
	rm -f $(OBJS) $(TARGET)
