#头文件带入
test: main.o sub.o
	gcc -o test main.o sub.o
%.o:%.c
	gcc -c -o $@ $<
sub.o:sub.c
	gcc -c -o sub.o sub.c

clean:
	rm *.o test
