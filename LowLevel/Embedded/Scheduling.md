# RTOS Scheduling Algorithms
## Rate Monotonic Scheduling (RMS)
* Type : Static priority Scheduling
* The task with the shortest periodicity executes with the highest priority.

Take the following example tasks:

T1 --> 3 (C), 20 (P)

T2 --> 2 (C), 5 (P)

T3 --> 2 (C), 10 (P)

Scheduling interval is LCM(20, 5, 10) = 20.

Priority : T2 > T3 > T1

## Earliest Deadline First (EDF)
* Type : Dynamic Priority Scheduling
* Task with the earliest deadline is executed first.
