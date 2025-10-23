CFLAGS = -O2 -g -Wall

tcp_client: tcp_client.c
	gcc $(CFLAGS) -o tcp_client tcp_client.c

tcp_echo: tcp_echo.o iouring.o
	gcc $(CFLAGS) -o tcp_echo tcp_echo.o iouring.o -luring

tcp_echo_threads: tcp_echo.o threads.o
	gcc $(CFLAGS) -o tcp_echo_threads tcp_echo.o threads.o


tcp_echo.o: tcp_echo.c
	gcc $(CFLAGS) -c -o tcp_echo.o tcp_echo.c

iouring.o: iouring.c
	gcc $(CFLAGS) -c -o iouring.o iouring.c

threads.o: threads.c
	gcc $(CFLAGS) -c -o threads.o threads.c

clean:
	rm -f tcp_client tcp_echo tcp_echo.o iouring.o