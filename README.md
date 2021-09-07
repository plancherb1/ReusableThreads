# ReusableThreads

A header only C++-11 indexable persistent threads library

This library is a mashup of threadpools and standard threads. Here we construct persistent threads that can each be sent specific jobs. 

This library is adapted from and inspired by [threadpool](https://github.com/PaulRitaldato1/ThreadPool) and [llvm](https://code.woboq.org/llvm/llvm/lib/Support/ThreadPool.cpp.html). 

## Usage and API:
```c++
// initialize
ReusableThreads<NUM_THREADS> threads;
// add a task where:
//    thread_id is an integer in range(0,NUM_THREADS)
//    varargs is a common seperated list of input arguments to the function specified by function_ptr
threads.addTask(thread_id, function_ptr, varargs);
// wait until all threads finish their tasks
threads->sync();
```