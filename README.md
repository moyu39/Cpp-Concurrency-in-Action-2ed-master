* C++11 引入了 Boost 线程库作为标准线程库，作者 Anthony Williams 为介绍其特性，于 2012 年出版了 *[C++ Concurrency in Action](https://book.douban.com/subject/4130141/)* 一书，并顺应 C++17 于 2019 年 2 月出版了[第二版](https://book.douban.com/subject/27036085/)。*[C++ Concurrency in Action 2ed](https://learning.oreilly.com/library/view/c-concurrency-in/9781617294693/)* 前五章介绍了[线程支持库](https://en.cppreference.com/w/cpp/thread)的基本用法，后六章从实践角度介绍了并发编程的设计思想，相比第一版多介绍了一些 C++17 特性，如 [std::scoped_lock](https://en.cppreference.com/w/cpp/thread/scoped_lock)、[std::shared_mutex](https://en.cppreference.com/w/cpp/thread/shared_mutex)，并多出一章（第十章）介绍 [C++17 标准库并行算法](https://en.cppreference.com/w/cpp/header/execution)，此外个人会在相应处补充 C++20 相关特性，如 [std::jthread](https://en.cppreference.com/w/cpp/thread/jthread)、[std::counting_semaphore](https://en.cppreference.com/w/cpp/thread/counting_semaphore)、[std::barrier](https://en.cppreference.com/w/cpp/thread/barrier)、[std::latch](https://en.cppreference.com/w/cpp/thread/latch) 等。阅读本书前可参考 [Andrew S. Tanenbaum](https://en.wikipedia.org/wiki/Andrew_S._Tanenbaum) 的 [*Modern Operating Systems*](https://book.douban.com/subject/25864553/)，预备操作系统的基础知识（[进程与线程](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/reference/processes_and_threads.md)、[死锁](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/reference/deadlocks.md)、[内存管理](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/reference/memory_management.md)、[文件系统](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/reference/file_systems.md)、[I/O](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/reference/IO.md) 等）。此为个人笔记，仅供参考，更详细内容见[原书](https://learning.oreilly.com/library/view/c-concurrency-in/9781617294693/)。

## [线程支持库](https://en.cppreference.com/w/cpp/thread)

1. [线程管理（Managing thread）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/01_managing_thread.md)：[\<thread\>](https://en.cppreference.com/w/cpp/header/thread)
2. [线程间共享数据（Sharing data between thread）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/02_sharing_data_between_thread.md)：[\<mutex\>](https://en.cppreference.com/w/cpp/header/mutex)、[\<shared_mutex\>](https://en.cppreference.com/w/cpp/header/shared_mutex)
3. [同步并发操作（Synchronizing concurrent operation）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/03_synchronizing_concurrent_operation.md)：[\<condition_variable\>](https://en.cppreference.com/w/cpp/header/condition_variable)、[\<semaphore\>](https://en.cppreference.com/w/cpp/header/semaphore)、[\<barrier\>](https://en.cppreference.com/w/cpp/header/barrier)、[\<latch\>](https://en.cppreference.com/w/cpp/header/latch)、[\<future\>](https://en.cppreference.com/w/cpp/header/future)、[\<chrono\>](https://en.cppreference.com/w/cpp/header/chrono)、[\<ratio\>](https://en.cppreference.com/w/cpp/header/ratio)
4. [C++ 内存模型和基于原子类型的操作（The C++ memory model and operations on atomic type）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/04_the_cpp_memory_model_and_operations_on_atomic_type.md)：[\<atomic\>](https://en.cppreference.com/w/cpp/header/atomic)

## 并发编程实践

5. [基于锁的并发数据结构的设计（Designing lock-based concurrent data structure）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/05_designing_lock_based_concurrent_data_structure.md)
6. [无锁并发数据结构的设计（Designing lock-free concurrent data structure）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/06_designing_lock_free_concurrent_data_structure.md)
7. [并发代码的设计（Designing concurrent code）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/07_designing_concurrent_code.md)
8. [高级线程管理（Advanced thread management）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/08_advanced_thread_management.md)
9. [并行算法（Parallel algorithm）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/09_parallel_algorithm.md)：[\<execution\>](https://en.cppreference.com/w/cpp/header/execution)
10. [多线程应用的测试与调试（Testing and debugging multithreaded application）](https://github.com/downdemo/Cpp-Concurrency-in-Action-2ed/blob/master/docs/10_testing_and_debugging_multithreaded_application.md)

## 标准库相关头文件

|头文件|说明|
|:-:|:-:|
|[\<thread\>](https://en.cppreference.com/w/cpp/header/thread)、[\<stop_token\>](https://en.cppreference.com/w/cpp/header/stop_token)|线程|
|[\<mutex\>](https://en.cppreference.com/w/cpp/header/mutex)、[\<shared_mutex\>](https://en.cppreference.com/w/cpp/header/shared_mutex)|锁|
|[\<condition_variable\>](https://en.cppreference.com/w/cpp/header/condition_variable)|条件变量|
|[\<semaphore\>](https://en.cppreference.com/w/cpp/header/semaphore)|信号量|
|[\<barrier\>](https://en.cppreference.com/w/cpp/header/barrier)、[\<latch\>](https://en.cppreference.com/w/cpp/header/latch)|屏障|
|[\<future\>](https://en.cppreference.com/w/cpp/header/future)|异步处理的结果|
|[\<chrono\>](https://en.cppreference.com/w/cpp/header/chrono)|时钟|
|[\<ratio\>](https://en.cppreference.com/w/cpp/header/ratio)|编译期有理数算数|
|[\<atomic\>](https://en.cppreference.com/w/cpp/header/atomic)|原子类型和原子操作|
|[\<execution\>](https://en.cppreference.com/w/cpp/header/execution)|标准库算法执行策略|

## 并发库对比

### [C++11 Thread](https://en.cppreference.com/w/cpp/thread)

|特性|API|
|:-:|:-:|
|thread|[std::thread](https://en.cppreference.com/w/cpp/thread/thread)|
|mutex|[std::mutex](https://en.cppreference.com/w/cpp/thread/mutex)、[std::lock_guard](https://en.cppreference.com/w/cpp/thread/lock_guard)、[std::unique_lock](https://en.cppreference.com/w/cpp/thread/unique_lock)|
|condition variable|[std::condition_variable](https://en.cppreference.com/w/cpp/thread/condition_variable)、[std::condition_variable_any](https://en.cppreference.com/w/cpp/thread/condition_variable_any)|
|atomic|[std::atomic](https://en.cppreference.com/w/cpp/atomic/atomic)、[std::atomic_thread_fence](https://en.cppreference.com/w/cpp/atomic/atomic_thread_fence)|
|future|[std::future](https://en.cppreference.com/w/cpp/thread/future)、[std::shared_future](https://en.cppreference.com/w/cpp/thread/shared_future)|
|interruption|无|

### [Boost Thread](https://www.boost.org/doc/libs/1_82_0/doc/html/thread.html)

|特性|API|
|:-:|:-:|
|thread|[boost::thread](https://www.boost.org/doc/libs/1_82_0/doc/html/thread/thread_management.html#thread.thread_management.thread)|
|mutex|[boost::mutex](https://www.boost.org/doc/libs/1_82_0/doc/html/thread/synchronization.html#thread.synchronization.mutex_types.mutex)、[boost::lock_guard](https://www.boost.org/doc/libs/1_82_0/doc/html/thread/synchronization.html#thread.synchronization.lock_guard.lock_guard)、[boost::unique_lock](https://www.boost.org/doc/libs/1_82_0/doc/html/thread/synchronization.html#thread.synchronization.locks.unique_lock)|
|condition variable|[boost::condition_variable](https://www.boost.org/doc/libs/1_82_0/doc/html/thread/synchronization.html#thread.synchronization.condvar_ref.condition_variable)、[boost::condition_variable_any](https://www.boost.org/doc/libs/1_82_0/doc/html/thread/synchronization.html#thread.synchronization.condvar_ref.condition_variable_any)|
|atomic|无|
|future|[boost::future](https://www.boost.org/doc/libs/1_82_0/doc/html/thread/synchronization.html#thread.synchronization.futures.reference.unique_future)、[boost::shared_future](https://www.boost.org/doc/libs/1_82_0/doc/html/thread/synchronization.html#thread.synchronization.futures.reference.shared_future)|
|interruption|[thread::interrupt](https://www.boost.org/doc/libs/1_82_0/doc/html/thread/thread_management.html#thread.thread_management.thread.interrupt)|

### [POSIX Thread](http://pubs.opengroup.org/onlinepubs/9699919799/basedefs/pthread.h.html)

|特性|API|
|:-:|:-:|
|thread|[pthread_create](http://pubs.opengroup.org/onlinepubs/9699919799/functions/pthread_create.html)、[pthread_detach](http://pubs.opengroup.org/onlinepubs/9699919799/functions/pthread_detach.html#)、[pthread_join](http://pubs.opengroup.org/onlinepubs/9699919799/functions/pthread_join.html#)|
|mutex|[pthread_mutex_lock、pthread_mutex_unlock](http://pubs.opengroup.org/onlinepubs/9699919799/functions/pthread_mutex_lock.html)|
|condition variable|[pthread_cond_wait](http://pubs.opengroup.org/onlinepubs/9699919799/functions/pthread_cond_wait.html)、[pthread_cond_signal](https://pubs.opengroup.org/onlinepubs/9699919799/functions/pthread_cond_signal.html)|
|atomic|无|
|future|无|
|interruption|[pthread_cancel](http://pubs.opengroup.org/onlinepubs/9699919799/functions/pthread_cancel.html)|

### [Java Thread](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/lang/Thread.html)

|特性|API|
|:-:|:-:|
|thread|[java.lang.Thread](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/lang/Thread.html)|
|mutex|[synchronized blocks](http://tutorials.jenkov.com/java-concurrency/synchronized.html)|
|condition variable|[java.lang.Object.wait](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/lang/Object.html#wait())、[java.lang.Object.notify](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/lang/Object.html#notify())|
|atomic|volatile 变量、[java.util.concurrent.atomic](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/util/concurrent/atomic/package-summary.html)|
|future|[java.util.concurrent.Future](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/util/concurrent/Future.html)|
|interruption|[java.lang.Thread.interrupt](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/lang/Thread.html#interrupt())|
|线程安全的容器|[java.util.concurrent](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/util/concurrent/package-summary.html) 中的容器|
|线程池|[java.util.concurrent.ThreadPoolExecutor](https://docs.oracle.com/en/java/javase/20/docs/api/java.base/java/util/concurrent/ThreadPoolExecutor.html)|
