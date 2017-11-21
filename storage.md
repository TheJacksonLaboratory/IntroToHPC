Ok, now that we are connecting to Helix through SSH, we should take a minute to examine and discuss the common directory structure of the system.

`/home` is where the home directories for every user are kept, and are accessible by all cluster nodes.  When you log in, you shold be in your `/home/userid` directory.  Let's check that by using `ssh` to connect back to Helix, and then using the `pwd` command we learned earlier.

~~~
ssh ssander@helix.jax.org
pwd
~~~

Home directories have a quota of 50GB each, meaning that the maximum storage available to a single user's `/home/userid` folder is 50GB.  

`/projects` is the primary active storage directory for users and lab groups.  It is accessible by all cluster nodes.  Users have a `/projects/userid` folder with a quota of 5TB, and each labgroup have a `/projects/PIname-lab` folder with a quota of 75TB.  Lab groups and services that require more space can work with the IT department for the acquisition and provisioning of additional storage capacity.

`/fastscratch` is a temporary directory pinned to the fastest in-house storage we have available.  It is accessible by all cluster nodes.  It has a total capacity of 100TB, and is meant to serve as 'scratch paper' for computational analysis.  Users can specify that their jobs output to `/fastscratch`, and then copy their important files back into their `/home` or `/project` directories.  Bioinformatics software can generate a large number of temporary and intermediate files, that are often no longer needed after the analysis completes, and can accidently consume large quantities of storage.  Files in the `/fastscratch` directory that have not been accessed in over 14 days or are over 30 days old will be erased automatically by the current storage system policy, and IT reserves the right to erase any and all data on `/fastscratch` without notice.

`/gt_delivery` is the delivery directory for sequence data from JAX's Genome Technologies group.  It is only available on the head nodes of Helix and Cadillac (`helix.jax.org` and `cadillac.jax.org`).  Data is accessible by group (so PIname-lab groups), and is automatically archived to long term storage by IT.
