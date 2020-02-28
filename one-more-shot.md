**CMSI 355** Networks, Spring 2020

# Assignment 0305
We continue to build up our network programming skills in this assignment, but with a fun twist: instead of programming something new in the same language, we program the same thing in a new language.

## Background Reading
Background reading remains the same overall for this assignment, except you are now likely to consult the complementary set of links from the ones that you consulted earlier. Refer to the [instructions from the prior assignment](https://github.com/lmu-cmsi355-spring2020/assignments/blob/master/one-shot.md) for those links.

## For Submission: Two One-Shot (or Few-Shot) Network Services…in Another Language
Port the two (2) software suites that you developed in the [preceding assignment](https://github.com/lmu-cmsi355-spring2020/assignments/blob/master/one-shot.md) to a new language. The ports should be identical at the protocol level, such that servers and clients from both implementations should be able to interact interchangeably.

_If you find that you need to change the network protocol during this port, please talk to me about it._ You would have to have a very compelling reason to do this in order for it to be necessary for this assignment.

Each software suite should contain the following:
* A server program—the program that, when running, listens for connections on a particular port and responds to requests sent over those connections
* A client program—a program that, when run, connects to a host that is running the server program, sends one or more requests based on user input (i.e., command-line parameters or standard input), and displays the result(s) to the user

Because the servers are supposed to be identical at the protocol level, you should be able to use the _exact same_ [Locust](https://locust.io) load-testing suite to exercise your server program. Thus, there is no need to re-submit the _locustfile.py_ files for this assignment, unless you found it necessary to change the network protocols of your services (and I approved of those changes). In that case, an updated _locustfile.py_ can be turned in, but it won’t get additional credit as it is considered to be solely a compatibility fix for the earlier version.

In addition to the software suite, you should still also provide (with one addition):
* Exported report files from a Locust load-test session
* Brief commentary on the Locust data, highlighting:
    1. The swarm size at which failures begin to manifest
    2. The maximum requests-per-second that your service was able to achieve
    3. The swarm size at which the host reached capacity (i.e., “Too many open files”)
    4. **Commentary on any observed differences between the performance of your servers in this language as opposed to the previous one—e.g., do you feel one tech stack has an advantage over another, and if so, in what areas? (performance, ease of programming, stability, etc.)**
    5. Any other observations/behaviors that you find notable

The fourth item is emphasized to highlight that it is new to this assignment, so don’t forget to include it.

Though not expressly graded, the use of `nc` while working on these programs is expected to be of great use in getting them to work correctly. `nc` interaction with your servers should be identical to `nc` interaction with these same servers from the previous assignment.

Due to now-increased familiarity with Locust, distributed Locust testing has been changed to “partial” extra credit—still worth 5 points, but only 3 of those are “extra” because the other point categories add up to 98, so doing distributed Locust would yield a maximum score of 103/100 if all other items get full credit. Opting out of distributed Locust produces a maximum score of 98/100.

You may continue to work with some classmates here, looking ahead to the full-scale network application for later in the semester. As before, however, you should still submit these servers individually.

### How to Turn it In
Create one folder per service in this repository, and place all files for that service within that folder. Each service folder should have at least the following files:
* Server code
* Client code
* Locust-related files
    * Exported Locust CSVs: statistics, response times, failures, exceptions
    * _locust-notes.md_: Markdown file containing your commentary on the load test results

## Specific Point Allocations
This assignment covers outcomes _2a_–_2c_, _3a_, _3b_, and _4a_–_4f_ as described in the [syllabus](http://dondi.lmu.build/spring2020/cmsi355/cmsi355-spring2020-syllabus.pdf). For this particular assignment, graded categories are as follows:

| Category | Points | Outcomes |
| -------- | -----: | -------- |
| Server code | 21 points each, 42 points total | _2b_, _2c_, _3a_, _3b_, _4a_–_4d_ |
| Client code | 21 points each, 42 points total | _2b_, _2c_, _3a_, _3b_, _4a_–_4d_ |
| Locust results | 2 points each, 4 points total | _2a_ |
| Locust commentary | 5 points each, 10 points total | _2a_, _2b_ |
| Distributed Locust | 5 points (potential 3 points extra credit) | _2a_ |
| Version Control | deduction only | _4e_ |
| Punctuality | deduction only | _4f_ |
| **Total** | **100** |
