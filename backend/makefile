FILE = fil

INCLDIR = ./include
CC = gcc
CFLAGS = -O2 -Wextra
CFLAGS += -I$(INCLDIR)

OBJDIR = obj

_DEPS = $(FILE).h
DEPS = $(patsubst %,$(INCLDIR)/%,$(_DEPS))

_OBJS = $(FILE).o
OBJS = $(patsubst %,$(OBJDIR)/%,$(_OBJS))

$(OBJDIR)/%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

$(FILE): $(OBJS)
	gcc -o $@ $^ $(CFLAGS)

$(SHA1): $(OBJS)
	gcc -o $@ $^ $(CFLAGS)

.PHONY: clean
clean:
	rm -f $(FILE) $(OBJDIR)/*.o *~ core $(INCLDIR)/*~
