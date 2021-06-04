# Data Science
### 1.1 data quality
* noise(modification of  original values) and ouliers(ouliers meaning independ point data)--> remove it before data analysis
* mising value
* duplicate data

### 1.2 handling missing value
* eliminate data objects
* eliminate missing values
* ignore it during data analysis
* replace with all possible value

### 1.3 


## Concurrency Control

### serial schedule
the actions of each transaction appear in same squence.
![img](img/1.0.png)

### equivalence class
- reads-from
wi(x) before rj(x), and there is no other wk(x) between them

- final write

#### View equivalence
- same reads-from 
- same final write
<img width="565" alt="Screenshot 2021-05-31 at 11 50 45" src="https://user-images.githubusercontent.com/30135516/120175365-709f1c00-c206-11eb-81c1-ce1844f0381c.png">
<img width="565" alt="Screenshot 2021-05-31 at 11 51 31" src="https://user-images.githubusercontent.com/30135516/120175468-8b719080-c206-11eb-8f1d-3f0d87d1aeb9.png">

#### conflict serializability
- same conflict set
- each conflict pair has same order

![igm](img/Screenshot%202021-06-03%20at%2015.45.39.png)

##### conflict graph
![screenshot](img/Screenshot%202021-06-03%20at%2015.50.06.png)
if acyclic(no cycle) then S is CSR(conflict serializability)


### Lock
- read lock
- write lock
  
#### Read-Lock
> Shared among different transaction
> followed by unlock


#### Write-Lock
> exclusive(not compatible不兼容的) 

#### Lock Manage
- conflict table
![screenshot](img/Screenshot%202021-06-03%20at%2016.40.18.png)

#### 2PL
> a transaction release any lock can't acquire a new lock

![screenshot](img/Screenshot%202021-06-03%20at%2016.43.17.png)
#### VSR, CSR, 2PL
![screenshot](img/Screenshot%202021-06-03%20at%2016.41.21.png)


### dead lock
![screenshot](img/Screenshot%202021-06-03%20at%2017.13.18.png)

#### dead lock detection
![screenshot](img/Screenshot%202021-06-03%20at%2017.16.00.png)

## Reliability Management

### Recovery
- dump
- checkpoint

#### dump
complete copy
> performed when system is offline
> stored in stable memory
> incremental
#### checkpoint
> writes data on disk for **all completed trasactions**
> Synchronous write
> records the **active trasactions**

#### 1. Warm restart
##### Redo
> which transaction is already finished but didn't commit, between the last checkpoint and fail.

##### Undo
> in the last checkponit

#### how to find the Redo and Undo
```
1. find the last checkpoint
at last checkpoint Undo = {all active transactions at last checkpoint}
Redo = { }(empty)

2. Read forward the log 
Undo = add the transaction which can find the Begin record
Redo = move transaction from the undo to redo when the commit record is found 
(transactions ending with rollback remain in undo list)
```
![redo-undo-begin](img/Screenshot%202021-06-04%20at%2009.54.31.png)
![redo-undo-end](img/Screenshot%202021-06-04%20at%2009.53.48.png)


#### 2. Cold restart

```
1. access the last dump to restore the damaged portion
2. starting the last dunp, and read the log and redo all the transactions and commit/rollback
3. perform a warm restart
(alternative 2 and 3)
```

> Require **two log reads**:
>- detect committed transactions(build Redo list)
>- Redo actions of transactions in redo list


