trafgen-libs =	$(shell pkg-config --libs libnl-3.0) \
		$(shell pkg-config --libs libnl-genl-3.0) \
		-lm

trafgen-objs =	xmalloc.o \
		ioops.o \
		privs.o \
		proc.o \
		dev.o \
		irq.o \
		link.o \
		str.o \
		sig.o \
		sock.o \
		mac80211.o \
		ring_tx.o \
		ring.o \
		timer.o \
		trafgen_lexer.yy.o \
		trafgen_parser.tab.o \
		trafgen.o

trafgen-lex =	trafgen_lexer.yy.o

trafgen-yaac =	trafgen_parser.tab.o

trafgen-eflags = $(shell pkg-config --cflags libnl-3.0) \
		 $(shell pkg-config --cflags libnl-genl-3.0) \
		 -DHAVE_DISSECTOR_PROTOS -I..

trafgen-confs =	trafgen_stddef.h

trafgen_post_install:
	$(Q)mv $(ETCDIRE)/trafgen_stddef.h $(ETCDIRE)/stddef.h

trafgen_clean_custom:
	$(Q)$(call RM,$(BUILD_DIR)/*.h $(BUILD_DIR)/*.c)
