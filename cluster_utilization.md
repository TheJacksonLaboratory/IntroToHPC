# Cluster Utilization

## HPC Live

[HPC Live](https://ctgraf01.jax.org/dashboard/db/hpc-dashboard?orgId=2&refresh=5m)

## Userspace Cluster Commands

showq
	(Show Queue)

Synopsis

showq [-b] [-g] [-l] [-c|-i|-r] [-p partition] [-R rsvid] [-v] [-w <CONSTRAINT>]

Overview
Displays information about active, eligible, blocked, and/or recently completed jobs.  Since the resource manager is not actually scheduling jobs, the job ordering it displays is not valid. The showq command displays the actual job ordering under the Moab Workload Manager.  When used without flags, this command displays all jobs in active, idle, and non-queued states.

Access
By default, this command can be run by any user.  However, the -c, -i, and -r flags can only be used by level 1, 2, or 3 Moab administrators.

Flags
Flag 	Description
-b 	display blocked jobs only
-c 	display details about recently completed jobs (see example, JOBCPURGETIME).
-g 	display grid job and system id's for all jobs.
-i 	display extended details about idle jobs. (see example)
-l 	display local/remote view. For use in a Grid environment, displays job usage of both local and remote compute resources.
-p 	display only jobs assigned to the specified partition.
-r 	display extended details about active (running) jobs. (see example)
-R 	display only jobs which overlap the specified reservation.
-v 	Display local and full resource manager job IDs as well as partitions. If specified with the '-i' option, will display job reservation time. .
-w 	display only jobs associated with the specified constraint. Valid constraints include user, group, acct, class, and qos. (see showq -w example.)

Details
   Beyond job information, the showq command will also report if the scheduler is stopped or paused or if a system reservation is in place. Further, the showq command will also report public system messages.

Examples

* Example 1: Default Report
* Example 2: Detailed Active/Running Job Report
* Example 3: Detailed Eligible/Idle Job Report
* Example 4: Detailed Completed Job Report

Example 1: Default Report
   The output of this command is divided into three parts, Active Jobs, Eligible Jobs, and Blocked Jobs.

```
> showq

active jobs------------------------
JOBID              USERNAME      STATE PROCS   REMAINING            STARTTIME

4415573                kimh    Running     8    00:31:09  Tue Dec 12 13:02:53
4416194              flynnb    Running     1     1:14:34  Tue Dec 12 12:46:18
4417125              tjongh    Running     1     1:51:11  Tue Dec 12 13:22:55
4417521                kimh    Running     8     1:54:22  Tue Dec 12 14:26:06
4417366               gongl    Running     1     2:00:22  Tue Dec 12 13:32:06
4417411               wongc    Running     1     2:03:11  Tue Dec 12 13:34:55
4417840            prashant    Running     1     2:30:21  Tue Dec 12 14:02:05
4417860                qzhu    Running     1     2:37:55  Tue Dec 12 14:09:39
4419443                kimh    Running     8     2:46:47  Tue Dec 12 15:18:31
4419581                kimh    Running     8     2:46:56  Tue Dec 12 15:18:40
4419812                kimh    Running     8     2:47:47  Tue Dec 12 15:19:31
4420022                kimh    Running     8     2:48:37  Tue Dec 12 15:20:21
4420126                kimh    Running     8     2:48:58  Tue Dec 12 15:20:42
4419896                kimh    Running     8     2:49:25  Tue Dec 12 15:21:09
4420995                kimh    Running     8     2:52:10  Tue Dec 12 15:23:54
4420616                kimh    Running     8     2:52:13  Tue Dec 12 15:23:57
4420874                kimh    Running     8     2:53:02  Tue Dec 12 15:24:46
4421155                kimh    Running     8     2:53:39  Tue Dec 12 15:25:23
4421101                kimh    Running     8     2:53:39  Tue Dec 12 15:25:23
4421127                kimh    Running     8     2:53:39  Tue Dec 12 15:25:23
4421158                kimh    Running     8     2:54:05  Tue Dec 12 15:25:49
4421414                kimh    Running     8     2:54:38  Tue Dec 12 15:26:22
4421411                kimh    Running     8     2:54:44  Tue Dec 12 15:26:28
4417815                kimh    Running     8     3:23:16  Tue Dec 12 13:55:00
4416180                kimh    Running     8     3:38:42  Tue Dec 12 14:10:26
4417862                kimh    Running     8     3:39:30  Tue Dec 12 14:11:14
4418840             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418850             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418844             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418838             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418845             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418842             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418848             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418851             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418841             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418837             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418839             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418846             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418849             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418847             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4418843             s-wangv    Running     8     3:40:01  Tue Dec 12 15:11:45
4415785                kimh    Running     8     3:41:17  Tue Dec 12 14:13:01
4416981                kimh    Running     8     3:43:50  Tue Dec 12 14:15:34
4417091                kimh    Running     8     3:54:20  Tue Dec 12 14:26:04
4417059                kimh    Running     8     3:56:36  Tue Dec 12 14:28:20
4416091                kimh    Running     8     4:01:08  Tue Dec 12 14:32:52
4417130                kimh    Running     8     4:02:44  Tue Dec 12 14:34:28
4414377                kimh    Running     8     4:23:18  Tue Dec 12 14:55:02
4414074                kimh    Running     8     4:28:32  Tue Dec 12 15:00:16
4413997                kimh    Running     8     4:30:01  Tue Dec 12 15:01:45
4414447                kimh    Running     8     4:30:14  Tue Dec 12 15:01:58
4414569                kimh    Running     8     4:32:16  Tue Dec 12 15:04:00
4417735                kimh    Running     8     4:46:22  Tue Dec 12 15:18:06
4417831                kimh    Running     8     4:49:13  Tue Dec 12 15:20:57
4417830                kimh    Running     8     4:49:13  Tue Dec 12 15:20:57
4417832                kimh    Running     8     4:49:13  Tue Dec 12 15:20:57
4421489                kimh    Running     8     4:53:51  Tue Dec 12 15:25:35
4421487                kimh    Running     8     4:53:51  Tue Dec 12 15:25:35
4417683                kimh    Running     8     4:55:52  Tue Dec 12 15:27:36
4419545                kimh    Running     8     4:57:34  Tue Dec 12 15:29:18
4421464                kimh    Running     8     4:59:01  Tue Dec 12 15:30:45
4421350                kimh    Running     8     4:59:29  Tue Dec 12 15:31:13
4413431                kimh    Running    12     7:36:05  Tue Dec 12 15:07:49
4413491                kimh    Running    12     7:36:31  Tue Dec 12 15:08:15
4419410                kimh    Running    12     7:49:22  Tue Dec 12 15:21:06
4413947                kimh    Running    12     7:50:49  Tue Dec 12 15:22:33
4414251                kimh    Running    12     7:51:45  Tue Dec 12 15:23:29
4414687                kimh    Running    12     7:56:06  Tue Dec 12 15:27:50
4414146                kimh    Running    12     7:57:28  Tue Dec 12 15:29:12
4414045                kimh    Running     8     8:42:27  Tue Dec 12 14:14:11
4414044                kimh    Running     8     8:42:51  Tue Dec 12 14:14:35
4417076                kimh    Running     8     9:29:32  Tue Dec 12 15:01:16
4417075                kimh    Running     8     9:29:46  Tue Dec 12 15:01:30
4419218                kimh    Running    20     9:53:19  Tue Dec 12 15:25:03
4419219                kimh    Running    20     9:54:08  Tue Dec 12 15:25:52
4419220                kimh    Running    20     9:54:29  Tue Dec 12 15:26:13
4419269                kimh    Running    20     9:54:47  Tue Dec 12 15:26:31
4419271                kimh    Running    20     9:55:11  Tue Dec 12 15:26:55
4419270                kimh    Running    20     9:55:20  Tue Dec 12 15:27:04
4417293                kimh    Running    12     9:59:01  Tue Dec 12 15:30:45
4420993                kimh    Running    20     9:59:23  Tue Dec 12 15:31:07
4420317            bleopold    Running     8    11:49:51  Tue Dec 12 15:21:35
4412323            bleopold    Running     1    18:25:09  Tue Dec 12 09:56:53
4421216            bleopold    Running     1    23:52:49  Tue Dec 12 15:24:33

252 active jobs       2241 of 5008 processors in use by local jobs (44.75%)
                         92 of 122 nodes active      (75.41%)
                         
eligible jobs----------------------
JOBID              USERNAME      STATE PROCS     WCLIMIT            QUEUETIME

4418355               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:12
4418357               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:12
4418354               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:07
4418356               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:12
4418478               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:31
4418468               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:26
4418376               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:13
4418426               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:20
4418516               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:37
4418447               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:25
4418417               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:19
4418424               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:19
4418461               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:26
4418438               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:25
4418552               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:38
4418509               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:32
4418523               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:38
4418419               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:19
4418546               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:38
4418361               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:12
4418495               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:32
4418505               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:32
4418366               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:12
4418541               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:38
4418493               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:32
4418482               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:31
4418414               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:19
4418459               wongc       Idle    16  2:00:00:00  Tue Dec 12 15:07:26

481 eligible jobs

blocked jobs-----------------------
JOBID              USERNAME      STATE PROCS     WCLIMIT            QUEUETIME

4400926               amins       Hold     4     4:00:00  Fri Dec  8 17:58:53
4400928               amins       Hold     4     1:10:00  Fri Dec  8 17:58:53
4420025                kimh       Hold     8     3:00:00  Tue Dec 12 15:20:19
4414079                kimh       Hold     8     5:00:00  Tue Dec 12 11:24:57
4417092                kimh       Hold     8     5:00:00  Tue Dec 12 13:16:33
4420074                kimh       Hold     8     3:00:00  Tue Dec 12 15:20:24
4414703                kimh       Hold     8     5:00:00  Tue Dec 12 11:43:15
4413500                kimh       Hold     8     5:00:00  Tue Dec 12 11:15:37
4419914                kimh       Hold     8     3:00:00  Tue Dec 12 15:19:50
4414378                kimh       Hold     8     5:00:00  Tue Dec 12 11:34:08
4419822                kimh       Hold     8     3:00:00  Tue Dec 12 15:19:28
4419577                kimh       Hold    12    12:00:00  Tue Dec 12 15:18:35
4419506                kimh       Hold    20    10:00:00  Tue Dec 12 15:18:30
4419691                kimh       Hold     8     5:00:00  Tue Dec 12 15:19:11
4421103                kimh       Hold     8     3:00:00  Tue Dec 12 15:24:12
4419438                kimh       Hold    12     5:00:00  Tue Dec 12 15:18:26
4413514                kimh       Hold     8     5:00:00  Tue Dec 12 11:15:37
4414406                kimh       Hold     8     5:00:00  Tue Dec 12 11:34:09
4420031                kimh       Hold     8     3:00:00  Tue Dec 12 15:20:20
4419689                kimh       Hold     8     5:00:00  Tue Dec 12 15:19:11
4414172                kimh       Hold     2    00:05:00  Tue Dec 12 11:28:17
4419592                kimh       Hold     8     3:00:00  Tue Dec 12 15:18:39
4419904                kimh       Hold     8     3:00:00  Tue Dec 12 15:19:49
4420878                kimh       Hold     8     3:00:00  Tue Dec 12 15:23:31
4420965                kimh       Hold     8     5:00:00  Tue Dec 12 15:23:44
4413961                kimh       Hold     8     5:00:00  Tue Dec 12 11:18:52
4413948                kimh       Hold     8     5:00:00  Tue Dec 12 11:18:51
4414590                kimh       Hold     8     5:00:00  Tue Dec 12 11:40:19
4414275                kimh       Hold     8     5:00:00  Tue Dec 12 11:31:24
4414589                kimh       Hold     8     5:00:00  Tue Dec 12 11:40:19
4414401                kimh       Hold     8     5:00:00  Tue Dec 12 11:34:09

809 blocked jobs

Total jobs:  1542
```

Active Jobs

Active jobs are those that are Running or Starting and consuming resources. Displayed are the job id*, the job's owner, and the job state.  Also displayed are the number of processors allocated to the job, the amount of time remaining until the job completes (given in HH:MM:SS notation), and the time the job started. All active jobs are sorted in "Earliest Completion Time First" order.

Note 	

*Job id's may be marked with a single character to to specify the following conditions:
Character 	Description
_ (underbar) 	job violates usage limit
* (asterisk) 	job is backfilled AND is preemptible
+ (plus) 	job is backfilled AND is NOT preemptible
- (hyphen) 	job is NOT backfilled AND is preemptible

Note 	Detailed active job information can be obtained using the '-r' flag.

Eligible Jobs

Eligible Jobs are those that are queued and eligible to be scheduled. They are all in the Idle job state and do not violate any fairness policies or have any job holds in place. The jobs in the Idle section display the same information as the Active Jobs section except that the wall clock CPULIMIT is specified rather than job time REMAINING, and job QUEUETIME is displayed rather than job STARTTIME. The jobs in this section are ordered by job priority. Jobs in this queue are considered eligible for both scheduling and backfilling.

Note 	Detailed eligible job information can be obtained using the '-i' flag.

Blocked Jobs

Blocked jobs are those that are ineligible to be run or queued. Jobs listed here could be in a number of states for the following reasons:

State 	Description
Idle 	Job violates a fairness policy. Use diagnose -q for more information.
UserHold 	A user hold is in place.
SystemHold 	An administrative or system hold is in place.
BatchHold 	A scheduler batch hold is in place (used when the job cannot be run because the requested resources are not available in the system or because the resource manager has repeatedly failed in attempts to start the job).
Deferred 	A scheduler defer hold is in place (a temporary hold used when a job has been unable to start after a specified number of attempts. This hold is automatically removed after a short period of time).
NotQueued 	Job is in the resource manager state NQ (indicating the job's controlling scheduling daemon in unavailable).

A summary of the job queue's status is provided at the end of the output.

Example 2: Detailed Active/Running Job Report
```
> showq -r

active jobs------------------------
JOBID               S  PAR  EFFIC  XFACTOR  Q  USERNAME    GROUP            MHOST PROCS   REMAINING            STARTTIME

4419224             R  tor ------      1.1  -      kimh  jaxuser         helix138     8     4:59:57  Tue Dec 12 15:35:20
4415573             R  tor  11.22      1.2  -      kimh  jaxuser         helix097     8    00:27:30  Tue Dec 12 13:02:53
4416194             R  tor   3.71      1.0  -    flynnb  jaxuser         helix106     1     1:10:55  Tue Dec 12 12:46:18
4417125             R  tor   8.40      1.0  -    tjongh  jaxuser         helix106     1     1:47:32  Tue Dec 12 13:22:55
4417521             R  tor  11.65      1.3  -      kimh  jaxuser         helix106     8     1:50:43  Tue Dec 12 14:26:06
4417411             R  tor  35.28      1.0  -     wongc  jaxuser         helix138     1     1:59:32  Tue Dec 12 13:34:55
4417840             R  tor 100.00      1.0  -  prashant  jaxuser         helix138     1     2:26:42  Tue Dec 12 14:02:05
4417860             R  tor 100.00      1.0  -      qzhu  jaxuser         helix135     1     2:34:16  Tue Dec 12 14:09:39
4419443             R  tor   5.37      1.0  -      kimh  jaxuser         helix097     8     2:43:08  Tue Dec 12 15:18:31
4419581             R  tor   9.68      1.0  -      kimh  jaxuser         helix087     8     2:43:17  Tue Dec 12 15:18:40
4419812             R  tor  10.54      1.0  -      kimh  jaxuser         helix134     8     2:44:08  Tue Dec 12 15:19:31
4420022             R  tor   9.84      1.0  -      kimh  jaxuser         helix132     8     2:44:58  Tue Dec 12 15:20:21
4420126             R  tor   9.84      1.0  -      kimh  jaxuser         helix132     8     2:45:19  Tue Dec 12 15:20:42
4419896             R  tor   9.69      1.0  -      kimh  jaxuser         helix127     8     2:45:46  Tue Dec 12 15:21:09
4420995             R  tor   9.95      1.0  -      kimh  jaxuser         helix124     8     2:48:31  Tue Dec 12 15:23:54
4420616             R  tor   9.35      1.0  -      kimh  jaxuser         helix123     8     2:48:34  Tue Dec 12 15:23:57
4420874             R  tor  10.04      1.0  -      kimh  jaxuser         helix106     8     2:49:23  Tue Dec 12 15:24:46
4421155             R  tor   9.78      1.0  -      kimh  jaxuser         helix124     8     2:50:00  Tue Dec 12 15:25:23
4421101             R  tor   9.06      1.0  -      kimh  jaxuser         helix126     8     2:50:00  Tue Dec 12 15:25:23
4421127             R  tor   9.56      1.0  -      kimh  jaxuser         helix125     8     2:50:00  Tue Dec 12 15:25:23
4421158             R  tor   9.77      1.0  -      kimh  jaxuser         helix131     8     2:50:26  Tue Dec 12 15:25:49
4421414             R  tor  10.14      1.0  -      kimh  jaxuser         helix132     8     2:50:59  Tue Dec 12 15:26:22
4421411             R  tor   8.52      1.0  -      kimh  jaxuser         helix137     8     2:51:05  Tue Dec 12 15:26:28
4417815             R  tor  11.75      1.0  -      kimh  jaxuser         helix131     8     3:19:37  Tue Dec 12 13:55:00
4416180             R  tor  11.81      1.3  -      kimh  jaxuser         helix132     8     3:35:03  Tue Dec 12 14:10:26
4417862             R  tor  11.53      1.0  -      kimh  jaxuser         helix126     8     3:35:51  Tue Dec 12 14:11:14
4418840             R  tor  12.00      1.0  -   s-wangv  jaxuser         helix096     8     3:36:22  Tue Dec 12 15:11:45
4418850             R  tor  11.99      1.0  -   s-wangv  jaxuser         helix133     8     3:36:22  Tue Dec 12 15:11:45
4418844             R  tor  11.99      1.0  -   s-wangv  jaxuser         helix135     8     3:36:22  Tue Dec 12 15:11:45
4418838             R  tor  12.00      1.0  -   s-wangv  jaxuser         helix096     8     3:36:22  Tue Dec 12 15:11:45
4418845             R  tor  11.98      1.0  -   s-wangv  jaxuser         helix134     8     3:36:22  Tue Dec 12 15:11:45
4418842             R  tor  11.99      1.0  -   s-wangv  jaxuser         helix135     8     3:36:22  Tue Dec 12 15:11:45
4418848             R  tor  11.99      1.0  -   s-wangv  jaxuser         helix133     8     3:36:22  Tue Dec 12 15:11:45
4418851             R  tor  11.99      1.0  -   s-wangv  jaxuser         helix133     8     3:36:22  Tue Dec 12 15:11:45
4418841             R  tor  11.99      1.0  -   s-wangv  jaxuser         helix137     8     3:36:22  Tue Dec 12 15:11:45
4418837             R  tor  12.03      1.0  -   s-wangv  jaxuser         helix106     8     3:36:22  Tue Dec 12 15:11:45
4418839             R  tor  12.00      1.0  -   s-wangv  jaxuser         helix096     8     3:36:22  Tue Dec 12 15:11:45
4418846             R  tor  11.98      1.0  -   s-wangv  jaxuser         helix134     8     3:36:22  Tue Dec 12 15:11:45
4418849             R  tor  11.99      1.0  -   s-wangv  jaxuser         helix133     8     3:36:22  Tue Dec 12 15:11:45
4418847             R  tor  11.98      1.0  -   s-wangv  jaxuser         helix134     8     3:36:22  Tue Dec 12 15:11:45
4418843             R  tor  11.99      1.0  -   s-wangv  jaxuser         helix135     8     3:36:22  Tue Dec 12 15:11:45
4415785             R  tor  11.62      1.3  -      kimh  jaxuser         helix126     8     3:37:38  Tue Dec 12 14:13:01

238 active jobs       2172 of 5008 processors in use by local jobs (43.37%)
                         91 of 122 nodes active      (74.59%)

Total jobs:  238
```

After displaying the running jobs, a summary is provided indicating the number of jobs, the number of allocated processors, and the system utilization.

```
> showq -i

eligible jobs----------------------
JOBID                 PRIORITY  XFACTOR  Q  USERNAME    GROUP  PROCS     WCLIMIT     CLASS      SYSTEMQUEUETIME

4418376*                    29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:13
4418377*                    29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:13
4418379*                    29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:13
4418378*                    29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:13
4418478                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:31
4418468                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:26
4418568                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:44
4418426                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:20
4418516                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:37
4418447                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:25
4418417                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418424                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418461                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:26
4418438                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:25
4418552                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418561                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:44
4418509                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:32
4418523                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418419                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418546                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418495                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:32
4418505                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:32
4418571                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:44
4418541                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418493                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:32
4418482                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:31
4418414                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418459                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:26
4418533                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418402                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418399                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418391                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:13
4418455                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:25
4418497                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:32
4418520                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418454                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:25
4418560                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:44
4418579                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:44
4418507                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:32
4418517                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:37
4418582                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:44
4418559                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:44
4418453                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:25
4418433                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:20
4418526                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418421                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418508                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:32
4418473                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:26
4418395                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418587                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:44
4418405                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418403                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418429                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:20
4418392                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:13
4418389                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:13
4418444                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:25
4418548                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418464                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:26
4418420                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:19
4418475                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:31
4418532                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418547                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418469                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:26
4418462                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:26
4418542                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418431                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:20
4418527                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38
4418458                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:25
4418501                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:32
4418460                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:26
4418545                     29      1.0  -     wongc  jaxuser     16  2:00:00:00     batch   Tue Dec 12 15:07:38

459 eligible jobs

Total jobs:  459
```

Note 	An asterisk at the end of a job (job 12956* in this example) indicates that the job has a job reservation created for it. The details of this reservation can be displayed using the checkjob command.

Example 4: Detailed Completed Job Report
```
> showq -c

completed jobs---------------------
JOBID               S CCODE         PAR  EFFIC  XFACTOR  Q  USERNAME    GROUP            MHOST PROCS    WALLTIME        COMPLETIONTIME

4416757             C 0             tor  77.35      1.0  -     wongc  jaxuser         helix112    16    00:19:46   Tue Dec 12 14:40:48
4414746             C 0             tor   6.00      1.3  -      kimh  jaxuser         helix134    12    00:06:48   Tue Dec 12 14:41:02
4416771             C 0             tor  84.02      1.0  -     wongc  jaxuser         helix089    16    00:17:47   Tue Dec 12 14:42:16
4414614             C 0             tor   5.78      1.3  -      kimh  jaxuser         helix136    12    00:07:18   Tue Dec 12 14:42:26
4416695             C 0             tor  43.23      1.0  -     wongc  jaxuser         helix110    16    00:36:59   Tue Dec 12 14:42:31
4416806             C 0             tor  66.61      1.0  -     wongc  jaxuser         helix100    16    00:08:38   Tue Dec 12 14:42:33
4416754             C 0             tor  58.98      1.0  -     wongc  jaxuser         helix031    16    00:22:16   Tue Dec 12 14:42:52
4416807             C 0             tor  62.75      1.0  -     wongc  jaxuser         helix052    16    00:08:41   Tue Dec 12 14:42:52
4418204             C 0             tor 104.39      1.0  -  bleopold  jaxuser         helix136     1    00:09:12   Tue Dec 12 14:43:01
4416824             C 0             tor   6.25      1.0  -     wongc  jaxuser         helix110    16    00:00:34   Tue Dec 12 14:43:07
4417804             C 0             tor  11.42      1.0  -      kimh  jaxuser         helix130     8    00:47:38   Tue Dec 12 14:43:52
4418205             C 0             tor 100.00      1.0  -  bleopold  jaxuser         helix106     1    00:01:02   Tue Dec 12 14:43:54
4414215             C 0             tor  10.32      2.5 me      kimh  jaxuser         helix096     8    00:15:33   Tue Dec 12 14:43:59
4416714             C 0             tor  66.28      1.0  -     wongc  jaxuser         helix012    16    00:32:49   Tue Dec 12 14:44:33
4414525             C 0             tor  22.97      1.6  -      kimh  jaxuser         helix137     8    00:11:32   Tue Dec 12 14:45:03
4414216             C 0             tor 100.00      2.6 me      kimh  jaxuser         helix106     1    00:01:07   Tue Dec 12 14:45:06
4416712             C 0             tor  61.04      1.0  -     wongc  jaxuser         helix111    16    00:33:52   Tue Dec 12 14:45:08
4416808             C 0             tor  64.49      1.0  -     wongc  jaxuser         helix042    16    00:10:38   Tue Dec 12 14:45:36
4416772             C 0             tor  87.91      1.0  -     wongc  jaxuser         helix078    16    00:21:05   Tue Dec 12 14:45:38
4414217             C 0             tor 100.00     40.0 me      kimh  jaxuser         helix106     1    00:00:37   Tue Dec 12 14:45:43
4416694             C 0             tor  45.22      1.0  -     wongc  jaxuser         helix027    16    00:40:19   Tue Dec 12 14:45:47
4416735             C 0             tor  60.94      1.0  -     wongc  jaxuser         helix083    16    00:28:42   Tue Dec 12 14:45:51
4417288             C 0             tor  10.44      1.2  -      kimh  jaxuser         helix138     8    00:18:17   Tue Dec 12 14:46:04
4416716             C 0             tor  63.70      1.0  -     wongc  jaxuser         helix056    16    00:34:22   Tue Dec 12 14:46:12
4417289             C 0             tor  10.51      1.2  -      kimh  jaxuser         helix137     8    00:18:36   Tue Dec 12 14:46:23
4416734             C 0             tor  56.61      1.0  -     wongc  jaxuser         helix030    16    00:29:58   Tue Dec 12 14:46:45
4417287             C 0             tor   9.89      1.2  -      kimh  jaxuser         helix138     8    00:19:02   Tue Dec 12 14:46:49
4416825             C 0             tor  65.23      1.0  -     wongc  jaxuser         helix100    16    00:04:18   Tue Dec 12 14:46:53
4414526             C 0             tor  23.84      1.6  -      kimh  jaxuser         helix133     8    00:11:28   Tue Dec 12 14:46:56
4413945             C 0             tor  34.63      1.3  -      kimh  jaxuser         helix135    20    00:30:42   Tue Dec 12 14:47:15
4416787             C 0             tor  75.95      1.0  -     wongc  jaxuser         helix041    16    00:19:24   Tue Dec 12 14:47:24
4414524             C 0             tor  22.72      1.6  -      kimh  jaxuser         helix133     8    00:11:58   Tue Dec 12 14:47:38
4416809             C 0             tor  61.96      1.0  -     wongc  jaxuser         helix055    16    00:12:39   Tue Dec 12 14:47:51
4416719             C 0             tor  58.61      1.0  -     wongc  jaxuser         helix115    16    00:34:21   Tue Dec 12 14:47:53
4414042             C 0             tor  10.82      1.3  -      kimh  jaxuser         helix138     8    00:48:18   Tue Dec 12 14:47:59
4416759             C 0             tor  76.70      1.0  -     wongc  jaxuser         helix039    16    00:26:51   Tue Dec 12 14:48:06
4416773             C 0             tor  79.32      1.0  -     wongc  jaxuser         helix015    16    00:23:31   Tue Dec 12 14:48:27
4417805             C 0             tor  18.17      1.9  -      kimh  jaxuser         helix106     4    00:05:01   Tue Dec 12 14:48:53
4418218             R CNCLD(271)      - ------      0.0  -      hoan  jaxuser                -     1    00:00:00   Tue Dec 12 14:48:59
4418217             C 1             tor   6.25      1.0  -      hoan  jaxuser         helix058    16    00:00:13   Tue Dec 12 14:48:59
4414041             C 0             tor  10.75      1.3  -      kimh  jaxuser         helix138     8    00:49:31   Tue Dec 12 14:49:34
4416826             C 0             tor  69.61      1.0  -     wongc  jaxuser         helix052    16    00:06:48   Tue Dec 12 14:49:42
4414043             C 0             tor  10.92      1.3  -      kimh  jaxuser         helix137     8    00:49:45   Tue Dec 12 14:49:42
4418109             C 0             tor  99.50      1.0  -     zhouw  jaxuser         helix036     1    00:21:35   Tue Dec 12 14:49:55
4416774             C 0             tor  87.74      1.0  -     wongc  jaxuser         helix029    16    00:24:58   Tue Dec 12 14:49:58

1447 completed jobs   (purgetime: 1:00:00)

Total jobs:  1447
```

After displaying the active jobs, a summary is provided indicating the number of jobs, the number of allocated processors, and the system utilization.

Note 	If the DISPLAYFLAGS parameter is set to ACCOUNTCENTRIC, job group information will be replaced with job account information.
