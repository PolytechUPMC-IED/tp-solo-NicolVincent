CFLAGS = -Wall
CFLAGS2 = -lz
CC = g++
CLIBS = /home/sasl/shared/main3/env/tools/include
LDLIBS = /home/sasl/shared/main3/env/tools/lib
PROGRAMS = id3v2 id3v2.o convert.o genre.o list.o

install : 
	cp /home/sasl/eleves/main/3672355/TP_solo/EnvDev/tp-solo-NicolVincent/id3v2-0.1.11/src/id3v2 /home/sasl/eleves/main/3672355/TP_solo/bin
	nroff -man /home/sasl/eleves/main/3672355/TP_solo/EnvDev/tp-solo-NicolVincent/id3v2-0.1.11/id3v2.1 > /home/sasl/eleves/main/3672355/TP_solo/man/man1/id3v2.1

all : $(PROGRAMS)

id3v2 : id3v2.o convert.o genre.o list.o
	$(CC) -L $(LDLIBS) $(CFLAGS) -o id3v2 id3v2.o convert.o genre.o list.o -lid3 $(CFLAGS2)
convert.o: convert.cpp
	$(CC) -I $(CLIBS) -DVERSION="\"${VERSION}\"" -c -o convert.o convert.cpp
genre.o: genre.cpp genre.h
	$(CC) -I $(CLIBS) -DVERSION="\"${VERSION}\"" -c -o genre.o genre.cpp
id3v2.o: id3v2.cpp
	$(CC) -I $(CLIBS) -DVERSION="\"${VERSION}\"" -c -o id3v2.o id3v2.cpp
list.o: list.cpp
	$(CC) -I $(CLIBS) -DVERSION="\"${VERSION}\"" -c -o list.o list.cpp
distclean:
	rm -f $(PROGRAMS)
	rm -f /home/sasl/eleves/main/3672355/TP_solo/man/man1/id3v2.1

.PHONY: all distclean install
