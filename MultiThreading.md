**MultiThreading:**

**Executor Framework:**
```
A framework having a bunch of components that are used for managing worker threads efficiently is referred to as Executor Framework. The Executor API reduces the execution of the task from the actual task to be executed through the Executors. 
The executor framework is an implementation of the Producer-Consumer pattern.

Executor framework is used to run the Runnable objects without creating new threads every time and also mostly re-using the already created threads


Types of Executors
SingleThreadExecutor. This thread pool executor has only a single thread. ...
FixedThreadPool(n) As the name indicates, it is a thread pool of a fixed number of threads. ...
CachedThreadPool. This thread pool is mostly used where there are lots of short-lived parallel tasks to be executed. ...
ScheduledExecutor.

Executor framework executes and processes the tasks asynchronously

```
https://deepakvadgama.com/blog/completable-future-internals/