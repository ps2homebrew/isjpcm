# _____     ___ ____     ___ ____
#  ____|   |    ____|   |        | |____|
# |     ___|   |____ ___|    ____| |    \    PS2DEV Open Source Project.
#-----------------------------------------------------------------------
# Copyright 2001-2005.
# Licenced under Academic Free License version 2.0
# Review ps2sdk README & LICENSE files for further details.
#-----------------------------------------------------------------------
# IOP_CFLAGS += -DNOPRINT (disable printf)
# IOP_CFLAGS += -DLIBSD (enable libsd/freesd based library)

IOP_OBJS_DIR = obj/
IOP_BIN_DIR = bin/
IOP_SRC_DIR = src/

IOP_BIN  = $(IOP_BIN_DIR)isjpcm.irx
IOP_OBJS = hw.o sjpcm_irx.o spu2.o imports.o

IOP_CFLAGS += -fno-builtin-printf
# IOP_CFLAGS += -DISJPCM
IOP_CFLAGS += -DLIBSD
IOP_INCS   += -I$(PS2SDK)/iop/include/ -I$(PS2SDK)/common/include/ -I$(PS2SDKSRC)/iop/sound/libsd/src/include/ -I./src/

all: $(IOP_OBJS_DIR) $(IOP_BIN_DIR) $(IOP_BIN) builtin

builtin:
	bin2c $(IOP_BIN) $(IOP_BIN_DIR)isjpcmIrx.c isjpcmIrx

$(IOP_OBJS_DIR):
	$(MKDIR) -p $(IOP_OBJS_DIR)

$(IOP_BIN_DIR):
	$(MKDIR) -p $(IOP_BIN_DIR)

$(IOP_LIB_DIR):
	$(MKDIR) -p $(IOP_LIB_DIR)

clean:
	rm -f -r $(IOP_OBJS_DIR) $(IOP_BIN_DIR)

install:
	mkdir -p $(DESTDIR)$(PS2DEV)/isjpcm/bin
	cp $(IOP_BIN) $(DESTDIR)$(PS2DEV)/isjpcm/bin

include $(PS2SDK)/Defs.make
include $(PS2SDK)/samples/Makefile.iopglobal

