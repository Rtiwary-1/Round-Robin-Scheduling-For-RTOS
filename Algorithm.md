## **Proposed Approach**
I have tried to come up with a modified round robin scheduling algorithm combined with priority scheduling algorithm which works on a dynamic time quantum, which changes after every round of execution. This will help in reducing the average waiting time, average turnaround time and reduce the number of context switch.
### My Contribution:
The early the shorter processes are removed from the ready queue, the better the turnaround time and the waiting time. So, in this algorithm, the shorter processes are given more time quantum so that they can finish their execution earlier. Here shorter processes are defined as the processes having less assumed CPU burst time than the previous process. Performance of RR algorithm solely depends upon the size of time quantum. If it is very small, it causes too many context switches. If it is very large, the algorithm degenerates to FCFS. So, this algorithm solves this problem by taking dynamic intelligent time quantum where the time quantum is repeatedly adjusted according to the shortness component and the priority component.
### Proposed Algorithm:
In this proposed approach, I calculate the dynamic time quantum using a parameter called Intelligence Time Slice (ITS) which allocates different time quantum to each process based on priority, shortest CPU burst time and context switch avoidance time. The ITS in turn is calculated using the following parameters:
Original Time Slice (OTS): Let the original time slice (OTS) be the time slice to be given to any process if it deserves no special consideration. 
Priority component (PC): Priority component (PC) is assigned 0 or 1 depending upon the priority assigned by the user which is inversely proportional to the priority number.
Shortness Component (SC): For Shortness Component (SC) difference between the burst time of current process and its previous process is calculated. If the difference is less than 0, then SC is assigned 1, else 0.
Context Switch Component (CSC): For calculation of Context Switch Component (CSC) first PC, SC and OTS is added and then their result is subtracted from the burst time. If this is less than OTS, it will be considered as Context Switch Component (CSC).
Adding all the values like OTS, PC, SC and CSC with burst time, the system will get intelligent time slice for individual process.

### **Algorithm**
Step 1: Start

Step 2: Input the number of processes followed by burst time, priority and initial time slice or initial time quantum.

Step 3: Sort the processes according to priority as well as shortness and assign a new priority to each process which is the sum of the original priority and shortness rank.

Step 4: Calculate priority component as follows:
If there are n processes, for a process i in n:
PCi=0 if its new priority is > 2n/3 (Not Important) 
PCi=1 if its new priority is > n/3 (Moderately Important) 
PCi=2 if its new priority is >= 1 (Important)

Step 5: Calculate shortness component as follows: 
If there are n processes, for a process i in n: 
SCi=0 if the (Burst Time)i > (Burst Time)i-1 (Longer) 
SCi=1 if the (Burst Time)i <= (Burst Time)i-1 (Shorter)

Step 6: Calculate the context switch component by adding PC, SC and OTS and then their result is subtracted from the burst time. If this is less than OTS, it will be considered as Context Switch Component (CSC).

Step 7: Calculate the intelligent time slice (ITS) for each process as the sum of the initial time slice, burst time, priority component, context switch component and shortness component.

Step 8: Calculate the dynamic time quantum. Let ‘TQi’ is be the time quantum in round i. The number of rounds i varies from 1 to n, where value of i increments by 1 after every round till ready queue is not equal to NULL. 
While(ready queue!= NULL)
{
    For i=1 to n do
    {
        if ( i ==1)
        {
            TQi = ½ ITS, if SC= 0
            TQi = ITS, otherwise
        }
    Else
    {
        TQi = 3/2 (TQi-1), if SC=0
            2 * (TQi-1), otherwise
        }
    If (remaining burst time - TQi )  <= 2
        TQi = remaining burst time
    }
    End of For
}
End of while

Step 9: Calculate the average waiting time and the average turnaround time.

Step 10: Stop
