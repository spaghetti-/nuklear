# Install
BIN = demo

# Flags
CFLAGS = -std=c99 -pedantic -O2

SRC = main.c
OBJ = $(SRC:.c=.o)

ifeq ($(OS),Windows_NT)
BIN := $(BIN).exe
LIBS = -lglfw3 -lopengl32 -lm -lGLU32 -lGLEW32
else
	UNAME_S := $(shell uname -s)
	ifeq ($(UNAME_S),Darwin)
		LIBS = -lglfw3 -framework OpenGL -lm -lGLEW
	else
    LIBS = -lglfw -lGL -lm -lGLU -lGLEW
	endif
endif

$(BIN):
	@mkdir -p bin
	rm -f bin/$(BIN) $(OBJS)
	$(CC) $(SRC) $(CFLAGS) -o bin/$(BIN) $(LIBS)
