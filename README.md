# bankersAlgorithm

Team members: Daniel Hernandez, Rudy Leiva

How to compile:

Linux/UNIX: Open terminal, cd to the directory where the source code file is stored. Run "gcc -o bankerAlgorithm bankerAlgorithm.c -pthread" (without quotes) on the terminal window. To run the program, simply do "./bankerAlgorithm <Resource 1> <Resource 2> <Resource 3> <run time>" (without quotes) (replace each <> with actual integer numbers). Example: ./bankerAlgorithm 10 5 7 50

Windows & Mac OS X: NOT COMPATIBLE - pthread(), and mutex() functions only available on Linux/UNIX.

Files included:

bankerAlgorithm.c (C source code)
bankerAlgorithm (C executable file)
output.txt (Text file that contains the output from running the program one time)

Description / purpose of program:

Project 4: This program is passed four command line arguments at the time of execution. The first 3 command line arguments are integers that define the available number of resources of resources R1, R2, and R3. The fourth argument defines how long the program will run. For this project, we are given that the maximum number of customers (threads) is five and that the maximum number or resources is three, so these numbers are hard coded into the project and some parts were coded for these particular numbers. The program next creates five customer threads, giving each thread a customer number (from 0 to 4). Once the threads are created, they begin execution and the main will sleep for the user specified time. Each customer thread contains its own customer number, so the customer thread function contains if blocks for each customer number. This is required to access the correct location of the 2D arrays. Each if block begins with the creation of a request array and populating it with random numbers that range from 0 to value stored in the array need and add 1 to that so that it's also possible to get the actual value stored in need as a request number. Next a call to request_resources() function is performed and passed the customer number and the request array. This function will perform the banker's algorithm to determin if the request can be granted or if its denied. If granted, resources are allocated and appropriate values are updated for available, allocated, and need arrays. If not a -1 is returned and the program will indicate that the requesting customer's request cant be granted due to insufficient resources. Now, regardless of a granted or denied request, the thread will sleep for a random amount of time units (from 0 to 5). If resources were allocated, the program indicates that resources are being used for that many time units. After the random sleep time has passed, the thread will now call release_resources() and pass it the customer number and a release array that contains the number of allocated resources. The function will check that there are indeed resources to release and update the appropriate entries in the avaiable, allocated, and need arrays. Each thread will continue to repeat this process of requesting resources and releasing resources until the user specified run time provided from the command line has elapsed.

Team member contribution:

Daniel Hernandez -

code development
code debugging
banker's algorithm research
threads and pointers research (stdint.h)
bankerAlgorithm.c
README

Rudy Leiva -

code development
code debugging
banker's algorithm research
threads and pointers research (stdint.h)
bankerAlgorithm.c
