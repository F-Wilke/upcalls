CFLAGS = -O0 -g -Wall -DDYN_KER_LINK

tcp_client: tcp_client.c
	gcc $(CFLAGS) -o tcp_client tcp_client.c

tcp_echo: tcp_echo.o iouring.o
	gcc $(CFLAGS) -o tcp_echo tcp_echo.o iouring.o -luring

tcp_echo_threads: tcp_echo.o threads.o
	gcc $(CFLAGS) -o tcp_echo_threads tcp_echo.o threads.o -L. -kallsyms

tcp_echo_uc: tcp_echo.o upcall.o libupcall.a
	gcc $(CFLAGS) -o tcp_echo_uc tcp_echo.o upcall.o libupcall.a -L. -lkallsyms



tcp_echo.o: tcp_echo.c
	gcc $(CFLAGS) -c -o tcp_echo.o tcp_echo.c

upcall.o: upcall.c
	gcc $(CFLAGS) -c -o upcall.o upcall.c


iouring.o: iouring.c
	gcc $(CFLAGS) -c -o iouring.o iouring.c

threads.o: threads.c
	gcc $(CFLAGS) -c -o threads.o threads.c


libupcall.a: ../libupcall/upcall.c
	gcc $(CFLAGS) -c -o ../libupcall/upcall.o ../libupcall/upcall.c
	ar cr libupcall.a ../libupcall/upcall.o



clean:
	rm -f tcp_client tcp_echo tcp_echo.o iouring.o threads.o tcp_echo_threads libupcall.a