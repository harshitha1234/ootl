Object Oriented Thread Library (C++)

Implemented a cross-platform object oriented threading library in C++ that supports

concurrent programming.

The library supports synchronization primitives such as mutex & conditional variables, and

handles event driven & interval based asynchronous threading, priority scheduling, etc.

In this project we created a C++ class that facilitated object orientated threading. The thread class had

the following attributes:

 It supports synchronization primitives such as mutex and conditional variables.
 It supports both event driven and interval based asynchronous threading.
 It supports both homogeneous and specialized threading.
 It provides a FCFS (First Come First Serve) stack-queue for posting and handling multiple tasks.

To support the new class, CThread, other supporting classes were also developed. The CMutexClass

and CEventClass provide resource management while the CTask class is a base class for deriving

classes that support homogeneous asynchronous threading.

The CMutexClass class encapsulates the system level mutex functions and a mutex synchronization

object. Mutex creation occurs during object instantiation with the mutex created as unblocked. The class

provides two member functions Lock and Unlock.

The CEventClass class encapsulates the Windows event functions, a Windows event object, UNIX

condition variable functions, and a UNIX condition variable. The functions encorporated into the

CEventClass class are SetEvent and CreateEvent under Windows, and phtread_cond_init,

pthread_cond_destroy, pthread_cond_signal, and pthread_cond_wait under UNIX. Event synchronization

objects are called condition variables under UNIX.

An Interval Driven thread is a thread that wakes up at predefined intervals, checks to see whether there is

a change in the environment, processes the changes in the environment, sleeps for the next interval, and

then wakes up and does it all over again. To implement an interval driven thread, you derive a CThread

class that redefines OnTask(LPVOID). Once the thread has been instantiated, you call the

SetThreadType member function with the parameter ThreadTypeIntervalDriven and an interval in

milliseconds.