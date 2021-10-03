# Round-Robin-Scheduling-For-RTOS
This repository contains the Optimized Round Robin Scheduling Algorithm with Dynamic Time Quantum for Real Time Operating System with proper explanation.

## __*Abstract*__: 
CPU scheduling is one of the most crucial operations performed by operating system. Different algorithms are available for CPU scheduling amongst them RR (Round Robin) is considered as optimal in time shared environment. The effectiveness of Round Robin completely depends on the choice of time quantum. In this paper a new CPU scheduling algorithm has been proposed, named as DABRR (Dynamic Average Burst Round Robin). That uses dynamic time quantum instead of static time quantum used in RR. The performance of the proposed algorithm is experimentally compared with traditional RR and some existing variants of RR. The results of our approach presented in this paper demonstrate improved performance in terms of average waiting time, average turnaround time, and context switching.

## __*INTRODUCTION*__:
Operating systems are resource managers. The resources managed by Operating systems are hardware, storage units, input devices, output devices and data. Operating systems perform many functions such as implementing user interface, sharing hardware among users, facilitating input/output, accounting for resource usage, organizing data, etc. Process scheduling is one of the functions performed by Operating systems. CPU scheduling is the task of selecting a process from the ready queue and allocating the CPU to it. Whenever CPU becomes idle, a waiting process from ready queue is selected and CPU is allocated to that. The performance of the scheduling algorithm mainly depends on CPU utilization, throughput, turnaround time, waiting time, response time, and context switch.
In RR a small unit of time is used which is called Time Quantum or Time slice. The CPU scheduler goes around the Ready Queue allocating the CPU to each process for a time interval up to 1-time quantum. If a process’s CPU burst exceeds 1-time quantum, that process is pre-empted and is put back in the ready queue. If a new process arrives then it is added to the tail of the circular queue. Out of the above discussed algorithms RR provides better performance as compared to the others in case of a time-sharing operating system. The performance of a scheduling algorithm depends upon the scheduling criteria viz. Turnaround time, Waiting time, Response time, CPU utilization, and throughput.

## THE PROCESS SCHEDULING OBJECTIVES ARE: -
*  Maximize throughput: A scheduling algorithm ought to be equipped for adjusting the greatest number of jobs per unit of time.
*  Avoid inconclusive blocking or starvation: A job ought not sit tight for unbounded time before or while process service.
*  Minimize overhead: Overhead causes wastage of assets. Be that as it may, when we utilize system resources viably, then general system execution enhances extraordinarily.
*  Enforcement of priorities: if system allocates priorities to forms, the booking system ought to support the higher need forms.
*  Attain balance between response, utilization: the scheduling algorithm must keep resources occupied
*  Support jobs which show desirable behaviour.
*  Corrupt gracefully under huge load.


## THE SCHEDULING CRITERIA’S: -
*  Context Switch: A context switch is process of storing and restoring context (state) of a pre-empted process, so that execution may be resumed from same point at a later stage. Context switching involves a lot of computation, lead to wastage of time and memory, which in turn increases the overhead of scheduler, hence operating system’s design, is to optimize only these switches.
*  Throughput: it is the number of processes completed per unit time. It is slow in round robin scheduling implementation. Context switching and throughput are inversely proportional.
*  CPU Utilization: Tells the business of the CPU. One needs to maximize CPU utilization.
*  Turnaround Time: Total time spent to complete the job. The time interval from the time of submission of a job to its completion is the turnaround time. Total turnaround time is the sum of the times spent waiting to get into memory, waiting time in the ready queue, execution time on the CPU and doing I/O.
*  Waiting Time: Time a job has been stalled in ready queue. The CPU scheduling algorithm does not affect the amount of time during which a process executes or does input-output; it affects only the amount of time that a process spends waiting in ready queue.
*  Response Time: in real time systems, turnaround time may not be best measure. Often, a job can provide with some output fairly early and continue computing new results while previous results are being produced to the user. Thus, it is the time from the submission of a request until the first response is produced that means time when the task is submitted until the first response is received. Thus, the response time should be less.
Hence for effective scheduling algorithm the following conditions should be maintained.
  *  less context switches.
  *  high CPU utilization.
  *  high throughput.
  *  Less turnaround time.
  *  Less waiting time.

## __*OVERVIEW OF THE PROPOSED SYSTEM:*__-
Response time of RR scheduling algorithm is relatively better, although its performance is very sensitive to time-slice. If quantum is very short, then the short processes will move through the system quickly and nicely. But if this quantum is so selected that it is not very large in comparison to process switching, then this
will invite more overhead of dispatching operations including process switches. To overcome all such drawbacks which hinder the better performance of CPU scheduling, new algorithm named OMDRRS “Optimum Multilevel Dynamic Round Robin Scheduling Algorithm” is proposed. This is a pre-emptive scheduling algorithm. OMDRRS algorithm calculates dynamic time slice after every round of execution. The results display robustness of this algorithm. It is an improvement of popularly implemented RR scheduling algorithm. And the process entering the ready state based on its arrival time, burst time and its priority with some weightages. The weightages which I have given is 20% to its arrival time, 30% to burst time and 40% to its priority and 10% to how effective is the dynamic time quantum is, which is suggested by analysing many processes with different values.

