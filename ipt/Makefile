CFLAGS = -I../src -fPIC
DESTDIR ?= /
XTABLES_LIB=$(shell pkg-config --variable=xtlibdir xtables)

all: libipt_FULLCONENAT.so
lib%.so: lib%.o
	$(CC) -shared -o $@ $^;
lib%.o: %lib%.c
	$(CC) ${CFLAGS} -D_INIT=lib$*_init -c -o $@ $<;
clean:
	rm -rf libipt_FULLCONENAT.so
install:
	install -D -v -m 644 libipt_FULLCONENAT.so $(DESTDIR)$(XTABLES_LIB)
uninstall:
	rm $(DESTDIR)$(XTABLES_LIB)/libipt_FULLCONENAT.so
