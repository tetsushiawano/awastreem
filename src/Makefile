CC = gcc

all : awastreem

.PHONY : all

test : all
	awastreem example.stm
.PHONY : test

y.tab.c : parse.y
	yacc parse.y

lex.yy.c : lex.l
	flex lex.l

parse.o : y.tab.c lex.yy.c
	$(CC) -g -c y.tab.c -o parse.o

awastreem : parse.o
	$(CC) -g parse.o -o awastreem

clean:
	rm -f y.output y.tab.c
	rm -f lex.yy.c
	rm -f *.o awastreem
.PHONY : clean
