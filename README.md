CPU-Scheduling-Algorithms

This project is an implementation of different CPU scheduling algorithms in C++. It covers First Come First Serve (FCFS), Round Robin (RR), Shortest Process Next (SPN), Shortest Remaining Time (SRT), Highest Response Ratio Next (HRRN), Feedback (FB), and Aging.

Table of Contents

CPU-Scheduling-Algorithms

Algorithms

First Come First Serve (FCFS)

Round Robin with varying time quantum (RR)

Shortest Process Next (SPN)

Shortest Remaining Time (SRT)

Highest Response Ratio Next (HRRN)

Feedback (FB)

Feedback with varying time quantum (FBV)

Aging

Input Format

Algorithms
First Come First Serve (FCFS)

FCFS is the simplest scheduling method where the process that comes first gets executed first. It is non-preemptive, meaning once a process starts, it runs until it finishes. While easy to use, it can cause long processes to delay shorter ones. This makes it better suited for batch systems where order of arrival matters.

Round Robin with varying time quantum (RR)

Round Robin (RR) divides CPU time fairly among processes using time slices called quanta. In this version, the time quantum is flexible and can change based on process needs. Short tasks can get smaller quanta, while longer ones get bigger.

Each process is placed in a queue. When its turn comes, it runs for the given quantum. If unfinished, it goes back to the queue.

By adjusting quantum values, RR helps reduce waiting times and avoids starvation.

Shortest Process Next (SPN)

SPN selects the process with the shortest burst time next. It is non-preemptive, so once a process begins, it runs till completion.

Processes are placed in a queue sorted by burst time, and the one with the least time is chosen first.

This method minimizes average waiting time but can delay long processes if many short ones keep arriving.

Shortest Remaining Time (SRT)

SRT is a preemptive version of SPN. Here, the process with the shortest remaining time is always chosen. If a new process arrives with less time than the current one, it preempts the CPU.

This helps reduce waiting time and adapts well when burst times are not known in advance.

Highest Response Ratio Next (HRRN)

HRRN is non-preemptive and selects processes based on their response ratio = (Waiting Time + Burst Time) / Burst Time.

The process with the highest ratio is executed first. This way, processes waiting longer get priority.

HRRN reduces waiting time and avoids starvation, especially when burst times are uncertain.

Feedback (FB)

Feedback scheduling uses multiple priority queues. Processes with higher priority are executed first. After execution, a process moves to a lower-priority queue.

This approach balances both short and long processes by giving urgent ones priority while ensuring others are eventually executed.

Feedback with varying time quantum (FBV)

FBV is similar to Feedback but uses different quantum values for each queue. Higher-priority processes get smaller quanta, while lower-priority ones get larger. This improves efficiency and fairness.

Aging

Aging is used to prevent starvation. In systems like Xinu, high-priority processes can block lower-priority ones forever. Aging solves this by slowly increasing the priority of waiting processes.

On each reschedule, the current process resets to its base priority, while all waiting processes gain +1 priority. Eventually, even low-priority processes reach the top and get CPU time.

Input Format

Line 1: "trace" or "stats"

Line 2: A comma-separated list of policies to analyze/visualize with parameters if needed. Example: 2-4 means RR with quantum 4, 8-1 means Aging with q=1.

FCFS

RR

SPN

SRT

HRRN

FB-1 (all queues q=1)

FB-2^i (queues with q=2^i)

Aging

Line 3: An integer for the last instant of the simulation.

Line 4: An integer for the number of processes.

Line 5+: Each process on a new line:

Process Name, Arrival Time, Service Time
