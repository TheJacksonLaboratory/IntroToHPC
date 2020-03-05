The high performance computing (HPC) resources of The Jackson Laboratory represent a shared resource available to all JAX researchers, and in order to keep these resources available to all researchers in a consistent and fair manner, a number of walltime-based queues have been implemented on these resources.  These queues allow the Information Technology department the ability to better plan maintenance and schedule upgrade windows on these systems, while providing a more consistent and stable operating environment for JAX HPC users.

### Identifying the partitions

### squeue

The squeue account provides details about many things including the partitions configured currently

~~~
squeue
squeue -u <username>
squeue --help
~~~

Examples:

squeue

~~~
JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
            643231       gpu RnnTrain   zhaoyu PD       0:00      1 (Resources)
            643232       gpu RnnTrain   zhaoyu PD       0:00      1 (Priority)
639633_[68-135%30]       gpu track_gr   sheppk PD       0:00      1 (JobArrayTaskLimit)
       552775_7337   compute checkBug   zhaoyu PD       0:00      1 (launch failed requeued held)
            627649   compute    build   tewher  R 1-03:00:18      1 sumner054
            627650   compute    build   tewher  R 1-03:00:18      1 sumner054
            627651   compute    build   tewher  R 1-03:00:18      1 sumner054
            627652   compute    build   tewher  R 1-03:00:18      1 sumner054
            627648   compute    build   tewher  R 1-03:00:28      1 sumner054
~~~

squeue -u tewher

~~~
JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
            627649   compute    build   tewher  R 1-03:02:14      1 sumner054
            627650   compute    build   tewher  R 1-03:02:14      1 sumner054
            627651   compute    build   tewher  R 1-03:02:14      1 sumner054
            627652   compute    build   tewher  R 1-03:02:14      1 sumner054
            627648   compute    build   tewher  R 1-03:02:24      1 sumner054
            638914   compute    build   tewher  R   22:07:11      1 sumner014
            638981   compute    build   tewher  R   22:07:11      1 sumner014
            638982   compute    build   tewher  R   22:07:11      1 sumner039
            638984   compute    build   tewher  R   22:07:11      1 sumner054
            638985   compute    build   tewher  R   22:07:11      1 sumner014
~~~

squeue --help

~~~
Usage: squeue [OPTIONS]
  -A, --account=account(s)        comma separated list of accounts
				  to view, default is all accounts
  -a, --all                       display jobs in hidden partitions
      --array-unique              display one unique pending job array
                                  element per line
      --federation                Report federated information if a member
                                  of one
  -h, --noheader                  no headers on output
      --hide                      do not display jobs in hidden partitions
  -i, --iterate=seconds           specify an interation period
  -j, --job=job(s)                comma separated list of jobs IDs
                                  to view, default is all
      --local                     Report information only about jobs on the
                                  local cluster. Overrides --federation.
  -l, --long                      long report
  -L, --licenses=(license names)  comma separated list of license names to view
  -M, --clusters=cluster_name     cluster to issue commands to.  Default is
                                  current cluster.  cluster with no name will
                                  reset to default. Implies --local.
  -n, --name=job_name(s)          comma separated list of job names to view
      --noconvert                 don't convert units from their original type
                                  (e.g. 2048M won't be converted to 2G).
  -o, --format=format             format specification
  -O, --Format=format             format specification
  -p, --partition=partition(s)    comma separated list of partitions
				  to view, default is all partitions
  -q, --qos=qos(s)                comma separated list of qos's
				  to view, default is all qos's
  -R, --reservation=name          reservation to view, default is all
  -r, --array                     display one job array element per line
      --sibling                   Report information about all sibling jobs
                                  on a federated cluster. Implies --federation.
  -s, --step=step(s)              comma separated list of job steps
				  to view, default is all
  -S, --sort=fields               comma separated list of fields to sort on
      --start                     print expected start times of pending jobs
  -t, --states=states             comma separated list of states to view,
				  default is pending and running,
				  '--states=all' reports all states
  -u, --user=user_name(s)         comma separated list of users to view
      --name=job_name(s)          comma separated list of job names to view
  -v, --verbose                   verbosity level
  -V, --version                   output version information and exit
  -w, --nodelist=hostlist         list of nodes to view, default is
				  all nodes

Help options:
  --help                          show this help message
  --usage                         display a brief summary of squeue options
~~~

### Identifying the QOS (Queues)

### `sacctmgr`

The `sacctmgr` (or Slurm Account Manager) command shows the current QOS (aka queues) on the HPC environment.

Examples:

sacctmgr

~~~
sacctmgr
sacctmgr show qos
sacctmgr --help
~~~

sacctmgr show qos

~~~
$ sacctmgr show qos
~~~

~~~
Name   Priority  GraceTime    Preempt PreemptMode                                    Flags UsageThres UsageFactor       GrpTRES   GrpTRESMins GrpTRESRunMin GrpJobs GrpSubmit     GrpWall       MaxTRES MaxTRESPerNode   MaxTRESMins     MaxWall     MaxTRESPU MaxJobsPU MaxSubmitPU     MaxTRESPA MaxJobsPA MaxSubmitPA       MinTRES
---------- ---------- ---------- ---------- ----------- ---------------------------------------- ---------- ----------- ------------- ------------- ------------- ------- --------- ----------- ------------- -------------- ------------- ----------- ------------- --------- ----------- ------------- --------- ----------- -------------
      long          0   00:00:00                cluster                                                        1.000000                                                                                                                    14-00:00:00      cpu=3600
     batch          0   00:00:00                cluster                                                        1.000000                                                                                                                     3-00:00:00      cpu=3600
~~~

sacctmgr  --help

~~~
$ sacctmgr --help
~~~

~~~
sacctmgr [<OPTION>] [<COMMAND>]
    Valid <OPTION> values are:
     -h or --help: equivalent to "help" command
     -i or --immediate: commit changes immediately
     -n or --noheader: no header will be added to the beginning of output
     -o or --oneliner: equivalent to "oneliner" command
     -p or --parsable: output will be '|' delimited with a '|' at the end
     -P or --parsable2: output will be '|' delimited without a '|' at the end
     -Q or --quiet: equivalent to "quiet" command
     -r or --readonly: equivalent to "readonly" command
     -s or --associations: equivalent to "associations" command
     -v or --verbose: equivalent to "verbose" command
     -V or --version: equivalent to "version" command

  <keyword> may be omitted from the execute line and sacctmgr will execute
  in interactive mode. It will process commands as entered until explicitly
  terminated.

  Valid <COMMAND> values are:
     add <ENTITY> <SPECS>     add entity
     archive <DUMP/LOAD> <SPECS>
                              Archive past jobs and/or steps, or load them
                              back into the databse.
     associations             when using show/list will list the
                              associations associated with the entity.
     clear stats              clear server statistics
     delete <ENTITY> <SPECS>  delete the specified entity(s)
     dump <CLUSTER> [File=<FILENAME>]
                              dump database information of the
                              specified cluster to the flat file.
                              Will default to clustername.cfg if no file
                              is given.
     exit                     terminate sacctmgr
     help                     print this description of use.
     list <ENTITY> [<SPECS>]  display info of identified entity, default
                              is display all.
     load <FILE> [<SPECS>]    read in the file to update the database
                              with the file contents. <SPECS> here consist
                              of 'cluster=', and 'clean'.  The 'cluster='
                              will override the cluster name given in the
                              file.  The 'clean' option will remove what is
                              already in the system for this cluster and
                              replace it with the file.  If the clean option
                              is not given only new additions or
                              modifications will be done, no deletions.
     modify <ENTITY> <SPECS>  modify entity
     oneliner                 report output one record per line.
     parsable                 output will be | delimited with an ending '|'
     parsable2                output will be | delimited without an ending '|'
     quiet                    print no messages other than error messages.
     quit                     terminate this command.
     readonly                 makes it so no modification can happen.
     reconfigure              reread the slurmdbd.conf on the DBD.
     shutdown                 shutdown the server.
     show                     same as list
     verbose                  enable detailed logging.
     version                  display tool version number.
     !!                       Repeat the last command entered.

  <ENTITY> may be "account", "association", "cluster",
                  "configuration", "coordinator", "event",
                  "federation", "job", "problem", "qos",
                  "resource", "reservation", "runawayjobs", "stats"
                  "transaction", "tres", "user" or "wckey"

  <SPECS> are different for each command entity pair.
       list account       - Clusters=, Descriptions=, Format=,
                            Names=, Organizations=, Parents=, WithAssoc,
                            WithDeleted, WithCoordinators, WithRawQOS,
                            and WOPLimits
       add account        - Clusters=, DefaultQOS=, Description=, Fairshare=,
                            GrpTRESMins=, GrpTRES=, GrpJobs=, GrpMemory=,
                            GrpNodes=, GrpSubmitJob=, GrpWall=, MaxTRESMins=,
                            MaxTRES=, MaxJobs=, MaxNodes=, MaxSubmitJobs=,
                            MaxWall=, Names=, Organization=, Parent=,
                            and QosLevel=
       modify account     - (set options) DefaultQOS=, Description=,
                            Fairshare=, GrpTRESMins=, GrpTRESRunMins=,
                            GrpTRES=, GrpJobs=, GrpMemory=, GrpNodes=,
                            GrpSubmitJob=, GrpWall=, MaxTRESMins=, MaxTRES=,
                            MaxJobs=, MaxNodes=, MaxSubmitJobs=, MaxWall=,
                            Names=, Organization=, Parent=, and QosLevel=
                            RawUsage= (with admin privileges only)
                            (where options) Clusters=, DefaultQOS=,
                            Descriptions=, Names=, Organizations=,
                            Parent=, and QosLevel=
       delete account     - Clusters=, DefaultQOS=, Descriptions=, Names=,
                            Organizations=, and Parents=

       list associations  - Accounts=, Clusters=, Format=, ID=, OnlyDefaults,
                            Partitions=, Parent=, Tree, Users=,
                            WithSubAccounts, WithDeleted, WOLimits,
                            WOPInfo, and WOPLimits

       list cluster       - Classification=, DefaultQOS=, Federation=,
                            Flags=, Format=, Names=, RPC= WithFed and
                            WOLimits
       add cluster        - DefaultQOS=, Fairshare=, Federation=, FedState=,
                            GrpTRES=, GrpJobs=, GrpMemory=, GrpNodes=,
                            GrpSubmitJob=, MaxTRESMins=, MaxJobs=,
                            MaxNodes=, MaxSubmitJobs=, MaxWall=, Name=,
                            QosLevel= and Weight=
       modify cluster     - (set options) DefaultQOS=, Fairshare=,
                            Federation=, FedState=, GrpTRES=, GrpJobs=,
                            GrpMemory=, GrpNodes=, GrpSubmitJob=,
                            MaxTRESMins=, MaxJobs=, MaxNodes=,
                            MaxSubmitJobs=, MaxWall=, QosLevel= and Weight=
                            (where options) Classification=, Federation=,
                            Flags=, and Names=
       delete cluster     - Classification=, DefaultQOS=, Flags=, and Names=

       add coordinator    - Accounts=, and Names=
       delete coordinator - Accounts=, and Names=

       list events        - All_Clusters, All_Time, Clusters=, End=, Events=,
                            Format=, MaxCPUs=, MinCPUs=, Nodes=, Reason=,
                            Start=, States=, and User=

       list federation    - Names=, Format= and Tree
       add federation     - Flags=, Clusters= and Name=
       modify federation  - (set options) Clusters= and Flags=
                            (where options) Names=
       delete federation  - Names=

       modify job         - (set options) DerivedExitCode=, Comment=
                            (where options) JobID=, Cluster=

       list qos           - Descriptions=, Format=, Id=, Names=,
                            PreemptMode=, and WithDeleted
       add qos            - Description=, Flags=, GraceTime=, GrpJobs=,
                            GrpSubmitJob=, GrpTRES=, GrpTRESMins=, GrpWall=,
                            MaxJobs=, MaxSubmitJobsPerUser=, MaxTRESMins=,
                            MaxTRESPerJob=, MaxTRESPerNode=, MaxTRESPerUser=,
                            MaxWall=, Names=, Preempt=, PreemptMode=,
                            Priority=, UsageFactor=, and UsageThreshold=
       modify qos         - (set options) Description=, Flags=, GraceTime=,
                            GrpJobs=, GrpSubmitJob=, GrpTRES=, GrpTRESMins=,
                            GrpWall=,
                            MaxJobs=, MaxSubmitJobsPerUser=, MaxTRESMins=,
                            MaxTRESPerJob=, MaxTRESPerNode=, MaxTRESPerUser=,
                            MaxWall=, Names=, Preempt=, PreemptMode=,
                            Priority=, RawUsage= (admin only),
                            UsageFactor=, and UsageThreshold=
                            (where options) Descriptions=, ID=, Names=
                            and PreemptMode=
       delete qos         - Descriptions=, ID=, Names=, and PreemptMode=

       list resource      - Clusters=, Descriptions=, Flags=, Format=, Ids=,
                            Names=, PercentAllowed=, ServerType=, Servers=,
                            and WithClusters
       add resource       - Clusters=, Count=, Descriptions=, Flags=,
                            ServerType=, Names=, PercentAllowed=, Server=,
                            and Type=
       modify resource    - (set options) Count=, Flags=, Manager=,
                            PercentAllowed=,
                            (where options) Clusters=, Names=, Servers=,
       delete resource    - Clusters=, Names=

       list reservation   - Clusters=, End=, ID=, Names=, Nodes=, Start=

       list runawayjobs   - Cluster=, Format=

       clear stats
       list stats

       list transactions  - Accounts=, Action=, Actor=, Clusters=, End=,
                            Format=, ID=, Start=, User=, and WithAssoc

       list tres          - ID=, Name=, Type=, WithDeleted

       list user          - AdminLevel=, DefaultAccount=,
                            DefaultWCKey=, Format=, Names=,
                            QosLevel=, WithAssoc, WithCoordinators,
                            WithDeleted, WithRawQOS, and WOPLimits
       add user           - Accounts=, AdminLevel=, Clusters=,
                            DefaultAccount=, DefaultQOS=, DefaultWCKey=,
                            Fairshare=, MaxTRESMins=, MaxTRES=,
                            MaxJobs=, MaxNodes=, MaxSubmitJobs=, MaxWall=,
                            Names=, Partitions=, and QosLevel=
       modify user        - (set options) AdminLevel=, DefaultAccount=,
                            DefaultQOS=, DefaultWCKey=, Fairshare=,
                            MaxTRESMins=, MaxTRES=, MaxJobs=, MaxNodes=,
                            MaxSubmitJobs=, MaxWall=, NewName=,
                            and QosLevel=,
                            RawUsage= (with admin privileges only)
                            (where options) Accounts=, AdminLevel=,
                            Clusters=, DefaultAccount=, Names=,
                            Partitions=, and QosLevel=
       delete user        - Accounts=, AdminLevel=, Clusters=,
                            DefaultAccount=, DefaultWCKey=, and Names=

       list wckey         - Clusters=, End=, Format=, ID=, Names=,
                            Start=, User=, and WithDeleted

       archive dump       - Directory=, Events, Jobs,
                            PurgeEventAfter=, PurgeJobAfter=,
                            PurgeStepAfter=, PurgeSuspendAfter=,
                            Script=, Steps, and Suspend

       archive load       - File=, or Insert=

  Format options are different for listing each entity pair.

  One can get an number of characters by following the field option with
  a %NUMBER option.  i.e. format=name%30 will print 30 chars of field name.

       Account            - Account, Coordinators, Description, Organization

       Association        - Account, Cluster, DefaultQOS, Fairshare,
                            GrpTRESMins, GrpTRESRunMins, GrpTRES, GrpJobs,
                            GrpMemory, GrpNodes, GrpSubmitJob, GrpWall,
                            ID, LFT, MaxTRESMins, MaxTRES,
                            MaxJobs, MaxNodes, MaxSubmitJobs, MaxWall, QOS,
                            ParentID, ParentName, Partition, RGT,
                            User, WithRawQOS

       Cluster            - Classification, Cluster, ClusterNodes,
                            ControlHost, ControlPort, DefaultQOS,
                            Fairshare, Flags, GrpTRESMins, GrpTRES GrpJobs,
                            GrpMemory, GrpNodes, GrpSubmitJob, MaxTRESMins,
                            MaxTRES, MaxJobs, MaxNodes, MaxSubmitJobs,
                            MaxWall, NodeCount, PluginIDSelect, RPC, TRES

       Event              - Cluster, ClusterNodes, Duration, End,
                            Event, EventRaw, NodeName, Reason, Start,
                            State, StateRaw, TRES, User

       QOS                - Description, Flags, GraceTime, GrpJobs,
                            GrpSubmitJob, GrpTRES, GrpTRESMins, GrpWall,
                            MaxJobs, MaxSubmitJobsPerUser, MaxTRESMins,
                            MaxTRESPerJob, MaxTRESPerNode, MaxTRESPerUser,
                            MaxWall, Name, Preempt, PreemptMode,
                            Priority, UsageFactor, UsageThreshold

       Resource           - Cluster, Count, CountAllowed, CountUsed,
                            Description, Flags, Manager, Name,
                            PercentAllowed, PercentUsed, Server, Type

       Reservation        - Assoc, Cluster, End, Flags, ID, Name,
                            NodeNames, Start, TRES, UnusedWall

       RunAwayJobs        - Cluster, ID, Name, Partition, State,
                            TimeStart, TimeEnd

       Transactions       - Action, Actor, Info, TimeStamp, Where

       TRES               - ID, Name, Type

       User               - AdminLevel, Coordinators, DefaultAccount,
                            DefaultWCKey, User

       WCKey              - Cluster, ID, Name, User

       Account/User WithAssoc option will also honor
       all of the options for Association.


  All commands entitys, and options are case-insensitive.
~~~


### Interactive Jobs 

* Currently no restrictions on interactive job count
* Jobs will run as long as the QOS allows

### Batch Queue (`batch`)

* Up to 700 cores running per user, max walltime = 48 hours.
* This queue allows users to submit a large number of medium-runtime, high-resource jobs to the Jax HPC clusters.  This queue does not allow interactivity.  Users should use interactivity available in the `interactive` queue. Jobs that do not specify a QOS will not be scheduled to run.

### Long Queue (`long`)

* 504 hours max walltime.
* This queue is where long-runtime jobs should be submitted.

### High Memory (`high_mem`)
  
* Jobs requiring greater then 512gb of memory.
* 72 hours max walltime.
* Please request approval to access the 'high_mem' queue via helpdesk. A cluster job ID will be required to confirm the requested access. A limited set of resources dedicated to running jobs that have memory requirements greater than 7 GB.  

### GPU (`gpu`)

* Interactivity allowed. Job arrays allowed.
* 72 hours max walltime.
* This queue is for jobs requiring NVIDIA GPU technology.  Jobs observed not utilizing GPU resources will be terminated without warning. A limited set of resources dedicated to running jobs that require GPU support.

### Special / Reserved Queue (`special`)

* The `special` queue is reserved for special requests by researchers in conjunction with the IT department.  Users should consult with IT if their jobs require more than 3 weeks to complete or have other needs that the above queues do not address.  Output showing the walltime exceeded from your job in the `long` queue or other reasons the job can not function within the existing queue configurations will be required.
