#### User configurable options #####
include ../../Makefile.config

.SUFFIXES: 
.SUFFIXES: .cpp .dp.cpp .c .o

EXEC = SeisAcoMod2D_one_API_V1.0.exe

Objects = main.o json_parser.o modelling_worker.o modelling_master.o read_receiver.o create_geometry.o \
          workload.o model.o check_stability.o gpu_modelling_kernels.dp.o gpumodelling.dp.o

all : $(EXEC)

$(EXEC):$(Objects)
	$(CPPLINKER) $(FFLAGS) -o $(EXEC) $(Objects) $(FLIBS) $(FFLAGS) -L/home/apps/cuda-10.2/lib64/ -lcudart
	mv $(EXEC) ../../../bin/

clean:
	rm -f *.o *~

#.cu.o:
#	nvcc $(NVFLAGS) -c $*.cu

.cpp.o:
	$(CPPC) $(FFLAGS) -c $*.cpp $(FLIBS) $(FFLAGS)

.dp.cpp:
	 $(CPPC) $(FFLAGS) -c $*.dp.cpp $(FLIBS) $(FFLAGS)

cleano:
	rm -f *.o *~	
