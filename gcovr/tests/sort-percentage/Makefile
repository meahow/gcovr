CFLAGS= -fprofile-arcs -ftest-coverage -fPIC

all:
	$(CXX) $(CFLAGS) -c file1.cpp -o file1.o
	$(CXX) $(CFLAGS) -c file2.cpp -o file2.o
	$(CXX) $(CFLAGS) -c file3.cpp -o file3.o
	$(CXX) $(CFLAGS) -c file4.cpp -o file4.o
	$(CXX) $(CFLAGS) -c main.cpp -o main.o
	$(CXX) $(CFLAGS) main.o file1.o file2.o file3.o file4.o -o testcase

run: txt xml html

GCOVR_TEST_OPTIONS = --sort-percentage

txt:
	./testcase
	$(GCOVR) $(GCOVR_TEST_OPTIONS) -d -o coverage.txt

xml:

html:
	./testcase
	$(GCOVR) $(GCOVR_TEST_OPTIONS) -d --html-details -o coverage.html

clean:
	rm -f testcase
	rm -f *.gc* *.o
	rm -f coverage.txt coverage.xml coverage*.html
