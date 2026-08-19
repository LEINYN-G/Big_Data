### Linux & Git for Data Engineering

#### _Overview_

This module establishes the Linux, command-line, shell scripting, and Git foundations required for working with large-scale data systems.

The objective is not to memorize Linux commands, but to understand how a data scientist or data engineer can use Linux and Git to build reproducible, observable, and maintainable data-processing systems.

This module forms the foundation for subsequent work with Hadoop, HDFS, MapReduce, Spark, and distributed data processing.

### *Real-World Problem*

Large-scale data systems depend heavily on the underlying operating environment.

Before processing data with Hadoop or other distributed frameworks, engineers need to answer questions such as:

- What operating system and kernel are being used?
- How much CPU and memory are available?
- Is sufficient disk space available for datasets?
- Which Java version is installed?
- Is Hadoop correctly configured?
- Which processes are consuming system resources?
- Can the environment be reproduced on another machine?
- Can experiments and changes be tracked reliably?

A failure in the underlying environment can affect the reliability and performance of a complete data-processing pipeline.

This project therefore treats Linux and Git as part of the data-engineering system rather than as separate tools.

---

**Objectives**

__Linux__

- Understand the Linux filesystem and directory structure
- Work effectively with the command line
- Understand file ownership and permissions
- Monitor CPU, memory, disk, and processes
- Investigate system and application logs
- Understand basic networking diagnostics
- Automate repetitive tasks using Bash

__Git__

- Understand repositories, commits, branches, and remotes
- Maintain meaningful commit history
- Use branches for isolated development
- Track experiments and code changes
- Practice reproducible development workflows
- Prepare for collaboration on open-source projects

---

### *Real-World Project*

Big Data Environment Health Monitor

The first practical project in this module is a lightweight Linux-based environment health monitor.

The tool collects information required to determine whether a machine is ready for Big Data experimentation.

Information Collected

The monitor will collect:

- Hostname
- Operating system
- Kernel version
- CPU information
- CPU utilization
- Total and available memory
- Disk capacity and usage
- Running processes
- Java version
- Git version
- Hadoop version
- Important Hadoop environment variables

Example Workflow

Linux System -> System Information
    |
     +---- CPU
     +---- Memory
     +---- Disk
     +---- Processes
     +---- Java
     +---- Git
     +---- Hadoop
     |
     ->
Health Report

---

__Why This Matters for Big Data?__

Hadoop and other distributed systems operate on machines whose CPU, memory, storage, networking, and software environments directly influence system behavior.

A simple environment-monitoring tool can therefore become the first layer of observability for later experiments.

The same principle will be extended in future modules to:

Linux
   ->
Hadoop / HDFS
   ->
MapReduce
   ->
Spark
   ->
Distributed Experiments
   ->
Performance Analysis

---

**Experiments**

#### Experiment 01 — System Information

Collect and report the basic characteristics of the development machine.

Questions:

- What hardware resources are available?
- Which Linux kernel is running?
- Which Java version is installed?
- Is Hadoop available from the command line?
- How much storage is available?

---

#### Experiment 02 — Resource Monitoring

Monitor system resources while executing a computational workload.

Metrics:

- CPU utilization
- Memory utilization
- Disk utilization
- Process execution time

Research question:

__How does system resource utilization change as computational workload increases?__

---

#### Experiment 03 — Log Analysis

Use Linux tools and shell scripting to analyze a structured log dataset.

Possible metrics:

- Number of events
- Number of errors
- Events per time interval
- Most frequent ev

### Research question:
Can lightweight command-line processing provide useful insights before introducing a distributed processing framework?

Technology Stack
Operating System : Ubuntu Linux
Shell            : Bash
Version Control  : Git
Language         : Bash / Java / Python
Big Data Target  : Hadoop

Git Workflow
Each meaningful change should be tracked using Git.
Example workflow:
git status
git add .
git commit -m "feat: add system health monitoring script"
git log -- oneline
git push

