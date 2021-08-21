---
title: Project 3 Multithreading
navbar: Guides
layout: guides
key: 2.3

assignments:
  - text: 'Project 3 Functionality'
    link: 'https://usfca.instructure.com/courses/1597848/assignments/7043805'

  - text: 'Project 3 Design'
    link: 'https://usfca.instructure.com/courses/1597848/assignments/7043813'

---

For this project, you will extend your [previous project](project-2.html) to support multithreading. In addition to meeting the previous project requirements, your code must make a thread-safe inverted index, and use a work queue to build and search an inverted index using multiple threads.

## Functionality

The core functionality of your project must satisfy the following requirements:

  - Maintain the functionality of the [previous project](project-2.html).

  - Process additional command-line parameters to determine whether to use multithreading and if so, how many threads to use in the work queue. See the [Input](#input) section for specifics.

  - Support the same output capability as before. See the [Output](#output) section for specifics.

  - Create a custom read/write lock class that allows multiple concurrent read operations, non-concurrent write and read/write operations, and allows an active writer to acquire additional read or write locks as necessary (i.e. reentrant write lock).

  - Create a new thread-safe inverted index using the custom read/write lock class above *in addition to* the original inverted index created for the previous projects.

  - Create a single work queue with finish and shutdown features. The work queue should not be initialized unless multithreading is enabled. If multithreading is enabled, the same work queue should be reused to multithread both the building and searching of the inverted index.

  - Use the work queue to build your inverted index from a directory of files using multiple worker threads. Each worker thread should parse a single file.

  - Use the work queue (same as the one used for building) to search your inverted index from a file of multiple word queries (for both exact and partial search). Each worker thread should handle an individual query (which may contain multiple words).

  - Exit gracefully (shutting down all worker threads) **without** calling `System.exit()` when all of the building and searching operations are complete.

  - Extend your classes from previous projects or create completely new classes to support multithreading. **DO NOT REMOVE YOUR SINGLE THREADING CODE**, as you still need to support single threaded building and searching the index.

  - You may *NOT* use any of the classes in the `java.util.concurrent` package and may *NOT* use the `Stream.parallel` method for the multithreaded code.

The functionality of your project will be evaluated with various JUnit tests. Please see the [Testing](#testing) section for specifics.

## Input

Your main method must be placed in a class named `Driver`. The `Driver` class should accept the following **additional** command-line arguments:

  - `-threads num` threads where `-threads` indicates the next argument `num` is the number of worker threads to use. If `num` is missing or an invalid number of threads are provided, please default to 5 threads.

    If the `-threads` flag is not provided, then assume your project should be single-threaded and should execute *exactly* as previous projects.

The command-line flag/value pairs may be provided in any order, and the order provided is not the same as the order you should perform the operations (i.e. always build the index before performing search, even if the flags are provided in the other order).

Your code should support all of the command-line arguments from the [previous project](project-2.html) as well.

## Output

The output of your inverted index and search results should be the same from the [previous project](project-2.html). As before, you should **only generate output files if the necessary flags are provided**.

## Testing

Unlike previous projects, you only have to pass 100% of the tests in the `Project3aTest.java` group of JUnit tests to satisfy the project functionality requirements and sign up for your first project 3 code review. This test group does NOT include the long-running runtime tests that benchmark your single- versus multi-threading code.

This is handled automatically by the Github Actions test script. If it detects a project `v3.0.x` release it will automatically run `Project3aTest.java`. For all other releases, like `v3.1.x`, it will run `Project3bTest.java` instead. This DOES include the long-running runtime tests that benchmark your code. Be prepared to wait!

You must pass `Project3bTest.java` for followup code reviews and to earn the project design grade. This includes getting a speedup of at least `1.1x` faster on average using multi-threading. However, it is possible to get speedups of `1.7x` faster or more.

<article class="message is-warning">
  <div class="message-body"><i class="far fa-stopwatch"></i>&nbsp;Be patient. The tests for project 3 can take some time to complete, even if you have an efficient approach.</div>
</article>

## Hints

It is important to develop the project iteratively. One possible breakdown of tasks are:

  - Get `log4j2` working and start adding debug messages in your code. Once you are certain a class is working, disable debug messages for that class in your `log4j2.xml` file.

  - Consider extending your previous inverted index to create a thread-safe version. You may need to add additional functionality to your single-threaded versions.

  - Create a thread-safe inverted index using the `synchronized` keyword. Do not worry about efficiency or using a custom lock class yet.

  - Modify how you build your index (both from a directory and from the web) to use multithreading and a work queue. Make sure you still pass the unit tests.

  - Modify how you search your index to use multithreading and a work queue. Make sure you still pass the unit tests.

  - Once you are sure this version works, convert your inverted index to use a custom read/write lock class *instead* of the `synchronized` keyword (don't use both). Make sure you still pass the unit tests.

  - Test your code in a multitude of settings and with different numbers of threads. Some issues will only come up occasionally, or only on certain systems.

  - Test your code with logging enabled, and then test your code with logging completely disabled. Your code will run faster without logging, which sometimes causes some concurrency problems.

  - Lastly, do not start on this project until you understand the multithreading code shown in class. If you are stuck on the code shown in class, PLEASE SEEK HELP. You do not need to figure it out on your own! You can ask the CS tutors, the teacher assistant, or the instructor for help.

**Do not worry about efficiency until after your first code review.** However, if you have had one code review and are running into issues, look for the following common issues:

  - Make sure the code does not over-notify (e.g. wake up threads more often than necessary).

  - Make sure the code does not over-finish (e.g. call finish more often than necessary).

  - Make sure the code does not over-block (e.g. perform blocking operations within a loop).

  - Make sure the code does not over-synchronize (e.g. preventing operations that could occur at the same time).

These issues are best detected using logging.

The important part will be to test your code as you go. The JUnit tests provided only test the entire project as a whole, not the individual parts. You are responsible for testing the individual parts themselves.
