LIBDIR=../lib
CXXFLAGS= -O -I.

target=$(LIBDIR)/libmodel_sm_ckm_qqttlpvl.a

all: $(target)

objects=HelAmps_sm_ckm_qqttlpvl.o Parameters_sm_ckm_qqttlpvl.o  ../../PROC_SA_CPP_sm_4/src/read_slha.o

$(target): $(objects)
	$(AR) cru $@ $(objects)
	ranlib $(target)

.PHONY: clean

clean:
	rm -f $(target)
	rm -f $(objects)

