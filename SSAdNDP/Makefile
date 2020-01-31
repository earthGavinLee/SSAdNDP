# Makefile created by mkmf $Id: mkmf,v 13.0 2006/04/10 21:20:01 fms Exp $ 

include Makefile.template


.DEFAULT:
	-touch $@
all: ssadndp.exe
ssadndp_module.o: ./ssadndp_module.f90 nbo_shared.o matutil.o periodic_matutil.o
	$(FC) $(FFLAGS) -c	./ssadndp_module.f90
diag.o: ./diag.f
	$(FC) $(FFLAGS) -c	./diag.f
nbo_main.o: ./nbo_main.f90 periodic_matutil.o nbo_shared.o matutil.o pre_nao.o nao.o nbo.o ssadndp_module.o
	$(FC) $(FFLAGS) -c	./nbo_main.f90
matutil.o: ./matutil.f90
	$(FC) $(FFLAGS) -c	./matutil.f90
nao.o: ./nao.f90 matutil.o nbo_shared.o sortutil.o
	$(FC) $(FFLAGS) -c	./nao.f90
nbo.o: ./nbo.f90 nbo_shared.o matutil.o periodic_matutil.o
	$(FC) $(FFLAGS) -c	./nbo.f90
periodic_matutil.o: ./periodic_matutil.f90 matutil.o
	$(FC) $(FFLAGS) -c	./periodic_matutil.f90
pre_nao.o: ./pre_nao.f90 matutil.o periodic_matutil.o nbo_shared.o sortutil.o
	$(FC) $(FFLAGS) -c	./pre_nao.f90
nbo_shared.o: ./nbo_shared.f90 matutil.o
	$(FC) $(FFLAGS) -c	./nbo_shared.f90
sortutil.o: ./sortutil.f90
	$(FC) $(FFLAGS) -c	./sortutil.f90
SRC = ./ssadndp_module.f90 ./diag.f ./nbo_main.f90 ./matutil.f90 ./nao.f90 ./nbo.f90 ./periodic_matutil.f90 ./pre_nao.f90 ./nbo_shared.f90 ./sortutil.f90
OBJ = ssadndp_module.o diag.o nbo_main.o matutil.o nao.o nbo.o periodic_matutil.o pre_nao.o nbo_shared.o sortutil.o
clean: neat
	-rm -f .cppdefs $(OBJ) ssadndp.exe
neat:
	-rm -f $(TMPFILES)
TAGS: $(SRC)
	etags $(SRC)
tags: $(SRC)
	ctags $(SRC)
ssadndp.exe: $(OBJ)
	$(LD) $(OBJ) -o ssadndp.exe $(LDFLAGS)
