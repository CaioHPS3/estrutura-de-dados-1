APPS = ./apps
BIN = ./bin
INCLUDE = ./include
LIB = ./lib
OBJ = ./obj
SRC = ./src

FLAGS = -O3 -Wall
LIBS = -lm -led -L $(LIB)



all: libed myapps

libed: \
	$(OBJ)/float_vector.o \
	$(OBJ)/mytime.o \
	$(OBJ)/linked_list.o \
	$(OBJ)/doubly_list.o \
	$(OBJ)/LDouble.o 

	ar -rcs $(LIB)/libed.a $(OBJ)/*.o


myapps: clean_apps \
	$(BIN)/test_float_vector \
	$(BIN)/test_linked_list \
	$(BIN)/test_doubly_list \
	$(BIN)/main

$(OBJ)/%.o: $(SRC)/%.c $(INCLUDE)/%.h
	gcc $(FLAGS) -c $< -I $(INCLUDE) -o $@

$(BIN)/%: $(APPS)/%.c
	gcc $(FLAGS) $< $(LIBS) -I $(INCLUDE) -o $@

run:
	$(BIN)/test_float_vector

clean:
	rm -rf $(BIN)/* $(LIB)/* $(OBJ)/*

clean_apps:
	rm -rf $(BIN)/*
