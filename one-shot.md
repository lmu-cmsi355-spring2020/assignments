**CMSI 355** Networks, Spring 2020

# Assignment 0225
It’s time for some network programming now, starting small then working our way up.

## Background Reading
We are sample-code driven for this assignment, so the primary references are Dr. Toal’s [Python](https://cs.lmu.edu/~ray/notes/pythonnetexamples/) and [JavaScript](https://cs.lmu.edu/~ray/notes/jsnetexamples/) network programming example pages. The [Java examples](https://cs.lmu.edu/~ray/notes/javanetexamples/), although not actively referenced in class, can provide some additional background too.

Library/framework reference documentation may also prove useful:
* Python: [socketserver](https://docs.python.org/3/library/socketserver.html), [socket](https://docs.python.org/3/library/socket.html)
* JavaScript: [net](https://nodejs.org/api/net.html)

For deeper background and details, Chapter 3 of the Comer book provides in-depth information on sockets and connections, while Chapter 4 talks about a number of real-world protocols (HTTP, IMAP, DNS, etc.) which may be particularly useful to those who are interested in pursuing the “work-alike” option.

## For Submission: Two One-Shot (or Few-Shot) Network Services
Develop two (2) software suites for a couple of “simple” network services that you implement at the socket level. “Simple” here is difficult to define—the closest we can get is to state that the services perform straightforward operations with very few protocol directives. Thus, the notion of “one-shot or few-shot” services.

Each software suite should contain the following:
* A server program—the program that, when running, listens for connections on a particular port and responds to requests sent over those connections
* A client program—a program that, when run, connects to a host that is running the server program, sends one or more requests based on user input (i.e., command-line parameters or standard input), and displays the result(s) to the user
* A [Locust](https://locust.io) load-testing suite which can exercise your server program with a reasonable profile of requests and operations

In addition to the software suite, you should also provide:
* Exported report files from a Locust load-test session (with extra credit if you do a distributed session with multiple machines swarming the same server)
* Brief commentary on the Locust data, highlighting:
    1. The swarm size at which failures begin to manifest
    2. The maximum requests-per-second that your service was able to achieve
    3. The swarm size at which the host reached capacity (i.e., “Too many open files”)
    4. Any other observations/behaviors that you find notable

Write both suites in the language of your choice—and note, for the next assignment, you will be asked to write these same services in a different language, so this is more a matter of sequencing than anything else.

Though not expressly graded, the use of `nc` while working on these programs is expected to be of great use in getting them to work correctly.

### Service Ideas
The following list provides some ideas for what will work as a “simple” service. One thought with these services is to use them as building blocks for the full-scale network application that will comprise the last assignments for the semester. This may save you some time later in the semester, or allow you to put together a more ambitious application because you’ve already implemented some portions of it.

| Potential Full-Scale Network Application | Possible Simple Services |
| -----------------------------------------| ------------------------ |
| role-playing/adventure game | multifunction dice roller |
|                             | grid/map navigator |
|                             | character roller |
| board game | board setup/basic moves |
|            | player joining/leaving |
|            | computer player setup |
| real-time game (e.g., two-player pong) | player coordinate tracker |
|                                        | game object tracker |
| card game | deck creator/shuffler/dealer |
|           | user hand creator/tracker |
|           | card hand evaluator (e.g., blackjack, poker—or whatever works for other types of decks) |
| chat room | connected user tracker |
|           | message send/receive |
|           | simple file send/receive |
| real-world protocol workalike | one-trick DNS |
|                               | hardcoded (but correct) HTTP |
|                               | simplified NTP |
| conversational bot | simple parsing/dictionary |
|                    | simple responses |
| translation/encryption service | simple parsing/dictionary |
|                                | simple key exchange |
| algorithm service (e.g., graphics calculations) | starter/simple operations |

This isn’t an exhaustive list, of course. Feel free to run additional ideas by me as needed. Note also that there is some overlap here and the same type of “simple” service might actually be useful in multiple types of network applications.

### Potential for Group Work
The full-scale network application at the end of the semester will be doable in groups. As such, for _this_ assignment, you can coordinate with a future groupmate so that you can “divide and conquer” the eventual full application by implementing some pieces under _individual_ submissions for this assignment. If you end up sharing some common scaffolding at this stage, for now just maintain your own copy of the common code in this repository.

Alternatively, you can do all of these assignments in isolation and not worry about future plans. You may also just decide to work fully on your own.

### How to Turn it In
Create one folder per service in this repository, and place all files for that service within that folder. Each service folder should have at least the following files:
* Server code
* Client code
* Locust-related files
    * _locustfile.py_
    * Exported Locust CSVs: statistics, response times, failures, exceptions
    * _locust-notes.md_: Markdown file containing your commentary on the load test results

## Specific Point Allocations
This assignment covers outcomes _2a_—_2c_, _3a_, _3b_, and _4a_–_4f_ as described in the [syllabus](http://dondi.lmu.build/spring2020/cmsi355/cmsi355-spring2020-syllabus.pdf). For this particular assignment, graded categories are as follows:

| Category | Points | Outcomes |
| -------- | -----: | -------- |
| Server code | 18 points each, 36 points total | _2b_, _2c_, _3a_, _3b_, _4a_–_4d_ |
| Client code | 18 points each, 36 points total | _2b_, _2c_, _3a_, _3b_, _4a_–_4d_ |
| Locust suite | 8 points each, 16 points total | _2a_, _2c_, _3a_, _3b_, _4a_–_4d_|
| Locust results | 2 points each, 4 points total | _2a_ |
| Locust commentary | 4 points each, 8 points total | _2a_, _2b_ |
| Distributed Locust | 5 points extra credit | _2a_ |
| Version Control | deduction only | _4e_ |
| Punctuality | deduction only | _4f_ |
| **Total** | **100** |

