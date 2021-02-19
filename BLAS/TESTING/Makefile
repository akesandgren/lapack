TOPSRCDIR = ../..
include $(TOPSRCDIR)/make.inc

.PHONY: all single double complex complex16
all: single double complex complex16
single:    xblat1s xblat2s xblat3s
double:    xblat1d xblat2d xblat3d
complex:   xblat1c xblat2c xblat3c
complex16: xblat1z xblat2z xblat3z

xblat1s: sblat1.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)
xblat1d: dblat1.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)
xblat1c: cblat1.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)
xblat1z: zblat1.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)

xblat2s: sblat2.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)
xblat2d: dblat2.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)
xblat2c: cblat2.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)
xblat2z: zblat2.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)

xblat3s: sblat3.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)
xblat3d: dblat3.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)
xblat3c: cblat3.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)
xblat3z: zblat3.o
	$(FC) $(FFLAGS_NOOPT) $(LDFLAGS) -o $@ $^ $(BLASLIB)

.PHONY: run
run: all
	./xblat1s > sblat1.out
	./xblat1d > dblat1.out
	./xblat1c > cblat1.out
	./xblat1z > zblat1.out
	./xblat2s < sblat2.in
	./xblat2d < dblat2.in
	./xblat2c < cblat2.in
	./xblat2z < zblat2.in
	./xblat3s < sblat3.in
	./xblat3d < dblat3.in
	./xblat3c < cblat3.in
	./xblat3z < zblat3.in

%.o: %.f
	$(FC) -c -o $@ $< $(FFLAGS_NOOPT)

.PHONY: clean cleanobj cleanexe cleantest
clean: cleanobj cleanexe cleantest
cleanobj:
	rm -f *.o
cleanexe:
	rm -f xblat*
cleantest:
	rm -f *.out core
