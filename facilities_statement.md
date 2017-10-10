# Research IT Resources

*Last Updated: 25-Sep-2017*

The Information Technology (IT) platforms at JAX enable computationally intensive, high-throughput, data-rich research to be conducted with the goal of developing personalized genomic medicine methodologies and practices.   The IT team supports our infrastructure and technology platforms, and includes several dedicated Research IT personnel.  Key IT platforms are summarized below:

## HPC in Bar Harbor, ME:

Cadillac is the HPC cluster serving researchers at the Bar Harbor, ME campus. 

Cadillac includes 32 HP Proliant SL Series servers with 20 cores at 2.5GHz and 256 GB RAM and 10 HP Proliant XL Series with 28 cores at 2.3GHz with 512 GB RAM combined into a 920-core high performance compute cluster.

Specialized resources associated with Cadillac include 2 nodes with 24 cores at 2.2GHz and 128 GB RAM with 4 GPU resources with 16 GB RAM each, for a combined total of 8 NVIDIA Tesla P100 Data Center Graphics Processing Units for a total of 28,672 CUDA processing cores.  An additional HP Proliant DL Series server with 48 cores at 3.0 GHz with 1,024 GB (1 TB) RAM is available for workloads with extremely large memory requirements.

A development server based on the HP Proliant DL Series platform is also available with 56 cores at 2.3GHz and 512 GB RAM.

Working storage (Tier 0) on Cadillac is provided by a Data Direct Networks Gridscalar GS7k GPFS storage appliance with 232 TB usable storage capacity.  The primary storage (Tier 1) on Cadillac is provided 25 Dell EMC Isilon scale-out NAS nodes combined for a total of 2.4 PB raw storage capacity.

## HPC in Farmington, CT:

Helix is the HPC cluster serving the Farmington, CT campus.

Helix includes 48 HP Proliant SL Series servers with 16 cores at 2.6GHz and 256 GB RAM, 48 HP Proliant SL Series servers with 20 cores at 2.5GHz and 256GB RAM, and 30 HP Proliant XL Series Servers with 28 cores at 2.6GHz and 512GB RAM combined into a 2,568-core high performance compute cluster.

Specialized resources associated with Helix include 2 nodes with 24 cores at 2.2GHz and 128 GB RAM with 4 GPU resources with 16 GB RAM each, for a combined total of 8 NVIDIA Tesla P100 Data Center Graphics Processing Units for a total of 28,672 CUDA processing cores.  An additional 2 HP Proliant DL Series servers with 64 cores at 2.5 GHz with 1,024 GB (1 TB) RAM is available for workloads with extremely large memory requirements.

A development server based on the HP Proliant DL Series platform is also available with 48 cores at 1.87GHz and 2,048 GB (2 TB) RAM.

Working storage (Tier 0) on Helix is provided by a Data Direct Networks Gridscalar GS7k GPFS storage appliance with 522 TB usable storage capacity.  The primary storage (Tier 1) on Helix is provided 27 Dell EMC Isilon scale-out NAS nodes combined for a total of 2.7 PB raw storage capacity.

## Archival Storage:

Archival storage (Tier 3) is provided at both Bar Harbor, ME and Farmington, CT by 2 Quantum Artico StorNext appliances with 72 TB front-end disk capacity backed by a 4 PB tape library at each site.  Data storage at this tier is replicated across both geographic sites.

## Applications Platform:

Our applications platform at both sites supports standard software necessary for investigators to process and analyze their data, as well as providing the entire research community with the basic building blocks for them to build their own custom workflows.  Database development and deployment is supported by MySQL and other database management systems.

## Network Infrastructure:

Our network platform at both sites supports both scientific and enterprise business systems, using 40Gb core switches in our server farm that delivers at least 1Gb to user devices.  The environment includes wired and wireless network service and a redundant voice over IP (VOIP) system, and is protected by application firewalls. The network infrastructure for the HPC environment is comprised of a 40Gb backbone with 40Gb to each server in the cluster, and 10Gb to each storage node.  Internet service is delivered by a commercial service provider that can scale beyond 10Gb as demand for data transfer increases.

## Scientific Services Support:

Gilbert is the HPC cluster serving the Genome Technologies Scientific Service.

Gilbert includes 10 HP Proliant XL Series servers with 28 cores at 2.3GHz and 512 GB RAM combined into a 280-core high performance compute cluster.  The primary storage (Tier 1) on Gilbert is provided by 10 Dell EMC Isilon scale-out NAS nodes combined for a total of 641.3 TB raw storage capacity.

Exome is the HPC cluster serving the Clinical Genomics Scientific Service.

Exome includes 8 HP Proliant SL Series servers with 16 cores at 2.6GHz and 256 GB RAM combined into a 128-core high performance compute cluster.  The primary storage (Tier 1) on Exome is provided by 4 Dell EMC Isilon scale-out NAS nodes combined for a total of 165.5 TB raw storage capacity.
