The high performance computing (HPC) resources of The Jackson Laboratory represent a shared resource available to all JAX researchers, and in order to keep these resources available to all researchers in a consistent and fair manner, a number of walltime-based queues have been implemented on these resources.  These queues allow the Information Technology department the ability to better plan maintenance and schedule upgrade windows on these systems, while providing a more consistent and stable operating environment for JAX HPC users.

### Identifying the Queues

### `qstat`

The `qstat` (or Queue Status) command shows the current state of all running jobs on the system.

Jobs are represented by JobIDs in the following format:

~~~
XXXXXXXX.helix-master.jax.org
~~~

where XXXXXXXX is a numeric identifier.

When used with the `-u userid` option, you can look at only the jobs being submitted to the queue by a particular user. When used with the `-f` option, the full information about the jobs running by a user can be identified.

Exercise: `qstat`
On the cluster, use qstat to see the list of all jobs being managed by the queue sytem, then pick a userid, and look at all jobs in the queue from a particular user.

Examples:

qstat

~~~
qstat
qstat -u ssander
qstat -f -u ssander
qstat XXXXXXXX.helix-master.jax.org
~~~

qstat -q

~~~
$ qstat -q
~~~

~~~
Queue            Memory CPU Time Walltime Node  Run Que Lm  State
---------------- ------ -------- -------- ----  --- --- --  -----
gpu                --      --    72:00:00   --    0   0 --   E R
long               --      --    504:00:0   --    0   0 --   E R
high_mem           --      --    72:00:00   --    1   0 --   E R
special            --      --       --      --    0   0 --   E R
test               --      --    72:00:00   --    0   0 --   E R
interactive        --      --    08:00:00   --    0   0 --   E R
batch              --      --    72:00:00   --  133   8 --   E R
                                               ----- -----
                                                 134     8
~~~

qstat -Q

~~~
$ qstat -Q
~~~

~~~
Queue              Max    Tot   Ena   Str   Que   Run   Hld   Wat   Trn   Ext T   Cpt
----------------   ---   ----    --    --   ---   ---   ---   ---   ---   --- -   ---
gpu                  0      0   yes   yes     0     0     0     0     0     0 E     0
long                 0      0   yes   yes     0     0     0     0     0     0 E     0
high_mem             0      1   yes   yes     0     1     0     0     0     0 E     0
special              0      0   yes   yes     0     0     0     0     0     0 E     0
test                 0      0   yes   yes     0     0     0     0     0     0 E     0
interactive          0      0   yes   yes     0     0     0     0     0     0 E     0
batch                0    142   yes   yes     0   133     8     0     0     0 E     1
~~~


### Interactive Queue (`interactive`)

* Interactivity allowed.  No job arrays allowed.
* 1 job, 8 hours.
* This queue allows limited interactivity for script development and troubleshooting, while the minimal walltime limits the amount of computational resources a single user can monopolize.

### Batch Queue (`batch`)

* No interactivity allowed. Job arrays allowed.
* 1000 queueable with 600 running per user, 72 hours.
* This queue allows users to submit a large number of medium-runtime, high-resource jobs to the Jax HPC clusters.  This queue does not allow interactivity.  Users should use interactivity available in the `interactive` queue or test their submissions on the appropriate cluster development nodes (`helix-dev.jax.org` or `cadillac-dev.jax.org`). Jobs that do not specify a queue will by default be run in the `batch` queue.

### Long Queue (`long`)

* No interactivity allowed. Job arrays allowed.
* 50 queueable with 5 running per user, 504 hours.
* This queue is where long-runtime jobs should be submitted.

### High Memory (`high_mem`)
  
* No interactivity allowed. Jobs requiring greater then 512gb of memory.
* 50 queueable with 5 running per user, 72 hours.
* Please request approval to access the 'high_mem' queue via helpdesk. A cluster job ID will be required to confirm the requested access. A limited set of resources dedicated to running jobs that have memory requirements greater than 512 GB.  

### GPU (`gpu`)

* Interactivity allowed. Job arrays allowed.
* 500 queueable with 200 running per user, 72 hours.
* This queue is for jobs requiring NVIDIA GPU technology.  Jobs observed not utilizing GPU resources will be terminated without warning. A limited set of resources dedicated to running jobs that require GPU support.

### Special / Reserved Queue (`special`)

* The `special` queue is reserved for special requests by researchers in conjunction with the IT department.  Users should consult with IT if their jobs require more than 3 weeks to complete or have other needs that the above queues do not address.  Output showing the walltime exceeded from your job in the `long` queue or other reasons the job can not function within the existing queue configurations will be required.
