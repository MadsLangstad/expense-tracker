# Compiler and flags
CC = gcc
CFLAGS = -I./include
LDFLAGS = -L/usr/lib -lm

# Directories
SRCDIR = src
INCDIR = include
OBJDIR = obj

# Source files
SRCS = $(wildcard $(SRCDIR)/*.c)

# Object files
OBJS = $(patsubst $(SRCDIR)/%.c,$(OBJDIR)/%.o,$(SRCS))

# Executable name
EXEC = backend_app

# Default target
all: $(EXEC)

# Link object files to create the executable
$(EXEC): $(OBJS)
	$(CC) $(OBJS) -o $@ $(LDFLAGS)

# Compile source files to object files
$(OBJDIR)/%.o: $(SRCDIR)/%.c
	$(CC) $(CFLAGS) -c $< -o $@

# Clean up object files and executable
clean:
	rm -f $(OBJDIR)/*.o $(EXEC)

# Phony targets
.PHONY: all clean


