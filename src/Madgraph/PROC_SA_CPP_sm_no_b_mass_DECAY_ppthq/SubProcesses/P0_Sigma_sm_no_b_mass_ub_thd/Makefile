LIBDIR=../../lib
INCDIR=../../src
MODELLIB=model_sm_no_b_mass_ppthq
CXXFLAGS= -O -I$(INCDIR) -I.
LIBFLAGS= -L$(LIBDIR) -l$(MODELLIB)

main=CPPProcess_P0_Sigma_sm_no_b_mass_ub_thd.o

all: $(main)

objects=CPPProcess_P0_Sigma_sm_no_b_mass_ub_thd.o 

#$(main): $(objects) $(LIBDIR)/lib$(MODELLIB).a
#	$(CXX) -o $@ $(objects) $(LIBFLAGS)

$(LIBDIR)/lib$(MODELLIB).a:
	cd ../../src
	make

.PHONY: clean

clean:
	rm -f $(target)
	rm -f $(objects)

