# Research IT Resources

*Last Updated: 26-Feb-2020*

The Information Technology (IT) platforms at JAX enable computationally intensive, high-throughput, data-rich research to be conducted with the goal of developing personalized genomic medicine methodologies and practices.   The IT team supports our infrastructure and technology platforms, and includes several dedicated Research IT personnel.  Key IT platforms are summarized below:



Working storage (Tier 0) on Cadillac is provided by a Data Direct Networks Gridscalar GS7k GPFS storage appliance with 232 TB usable storage capacity.  The primary storage (Tier 1) on Cadillac is provided 25 Dell EMC Isilon scale-out NAS nodes combined for a total of 2.4 PB raw storage capacity.  A new storage array (Tier 2) has been brought online as of Q1 2018 adding approximately 2 PB of new non-computable capacity.

## HPC Resources for all JAX Research:

## Sumner Cluster:

Sumner is the HPC cluster physically located at the Farmington, CT campus.

Sumner includes 100 Supermicro X11DPT-B Series servers with 70 Intel Xeon Gold 6150 computable cores at 2.7GHz and 768 GB RAM creating a 7,000-core high performance compute cluster.

Specialized resources associated with Sumner include 2 nodes with 142 Intel Xeon Gold 6150 cores at 2.7GHz and 3 TB RAM available for workloads with extremely large memory requirements.

## Winter Cluster:

Winter includes 8 Supermicro X11DGQ Series servers with 46 Intel Xeon Gold 6136 at 3.00GHz and 192 GB RAM.  Each server includes 4 Nvidia Tesla V100 32 GB GPU nvme cards.  This translates into 249.6 TFLOPS of double precision floating-point, 502.4 TFLOPS of single precision and 4,000 Tensor TFLOPS of combined, peak performance.

## Cluster Accessible Storage:

Working storage (Tier 0) on Sumner is provided by a Data Direct Networks Gridscalar GS7k GPFS storage appliance with 522 TB usable storage capacity.  The primary storage (Tier 1) on Sumner is provided 27 Dell EMC Isilon scale-out NAS nodes combined for a total of 2.7 PB raw storage capacity.  A new storage array (Tier 2) has been brought online as of Q1 2018 adding approximately 2 PB of new non-computable capacity.

## Archival Storage:

Archival storage (Tier 3) is provided at both Bar Harbor, ME and Farmington, CT by 2 Quantum Artico StorNext appliances with 72 TB front-end disk capacity backed by a 4 PB tape library at each site.  Data storage at this tier is replicated across both geographic sites.

## Applications Platform:

Our applications platform at both sites supports standard software necessary for investigators to process and analyze their data, as well as providing the entire research community with the basic building blocks for them to build their own custom workflows.  Database development and deployment is supported by MySQL and other database management systems.

## Network Infrastructure:

Our network platform supports scientific and enterprise business systems, using 40Gb core switches in our server farm that delivers at least 1Gb to user devices.  The environment includes wired and wireless network service and a redundant voice over IP (VOIP) system, and is protected by application firewalls. The network infrastructure for the HPC environment is comprised of a dedicated 100Gb backbone with 50Gb to each server in the cluster, and 40Gb to each storage node.  Internet service is delivered by a commercial service provider that can scale beyond 10Gb as demand for data transfer increases.

## Scientific Services Support:

Gilbert is the HPC cluster serving the Genome Technologies Scientific Service.

Gilbert includes 10 HP Proliant XL Series servers with 28 cores at 2.3GHz and 512 GB RAM combined into a 280-core high performance compute cluster.  The primary storage (Tier 1) on Gilbert is provided by 10 Dell EMC Isilon scale-out NAS nodes combined for a total of 641.3 TB raw storage capacity.

Exome is the HPC cluster serving the Clinical Genomics Scientific Service.

Exome includes 8 HP Proliant SL Series servers with 16 cores at 2.6GHz and 256 GB RAM combined into a 128-core high performance compute cluster.  The primary storage (Tier 1) on Exome is provided by 4 Dell EMC Isilon scale-out NAS nodes combined for a total of 165.5 TB raw storage capacity.
