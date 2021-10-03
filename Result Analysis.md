## **Result Analysis:**

### INPUT
------------------------------------
Process No. |	1	| 2	| 3	| 4	| 5
Burst Time	| 80	| 60	| 65	| 120	| 30
Priority	| 1	| 3	| 2	| 4	| 5

### Output obtained by Proposed Algorithm
ITS	| 86	| 67	| 71	| 126	| 37
Round | 1	| 80	| 60	| 35	| 62	| 30
Round | 2	| 0	| 0	| 30	| 58	| 0
Waiting Time	| 0	| 80	| 232	| 235	| 175
Turnaround Time	| 80	| 140	| 297	| 355	| 205

### Output obtained by Round Robin Scheduling Algorithm
Waiting Time	| 231	| 202	| 222	| 235	| 128
Turnaround Time	| 311	| 262	| 287	| 355	| 158

### Output obtained by Priority Scheduling Algorithm
Waiting Time	| 0	| 80	| 145	| 205	| 325
Turnaround Time	| 80	| 145	| 205	| 325	| 355


## **Comparison**
Process No.	| 1	| 2	| 3	| 4	| 5	| Average
------------| --| --| --|--| --| -------- 
Proposed Algorithm	| Waiting Time	0	80	232	235	175	144.40
	                    Turnaround Time	80	140	297	355	205	215.40
Round Robin	Waiting Time	231	202	222	235	128	203.60
	Turnaround Time	311	262	287	355	158	274.60
Priority Scheduling	Waiting Time	0	80	145	205	325	151.00
	Turnaround Time	80	145	205	325	355	222.00


 
 

 
Thus, we observe that the proposed algorithm has less Average waiting time and Average turnaround time as compared to Round Robin and Priority Scheduling Algorithms.
