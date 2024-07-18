# Kubernetes Job

Hi! shadow this side today we are going to deploy Kubernetes jobs i am going to teach you about kubernetes jobs and their types and how they works.
**So let's go**

# Jobs

Jobs in Kubernetes are versatile for running batch processes and tasks that require completion. By understanding their types and configuring them appropriately through Kubernetes manifests, you can effectively manage batch workloads within your Kubernetes clusters. Each type of Job serves different use cases, from sequential to parallel execution, and even scheduled recurring tasks, providing flexibility and scalability for various workload requirements.

## Content

- [non-parallel-job.yaml](https://github.com/shadowsince1999/Kubernetes/blob/main/Jobs/non-parallel-job.yaml "non-parallel-job.yaml")
- [parallel-job.yaml](https://github.com/shadowsince1999/Kubernetes/blob/main/Jobs/parallel-job.yaml "parallel-job.yaml")
- [scheduled-job.yaml](https://github.com/shadowsince1999/Kubernetes/blob/main/Jobs/scheduled-job.yaml "scheduled-job.yaml")

## What are all these files ?

**Ok so i will make it easy for you** basically these all files are k8s jobs manifests which help us to ctreate diff type of jobs in k8s i am going to define main 3 type of jobs in this repo.

# Files :- 

## Non-parallel-job.yaml

A **non-parallel Job** in Kubernetes is a type of Job configuration where only one Pod is created and run to completion. This means that Kubernetes will ensure that a single instance of the specified Pod completes its task successfully before considering the Job complete.

**Usage Scenarios**:

-   Useful for tasks that need to be executed sequentially and cannot be parallelized.
-   Suitable for batch processing scenarios where tasks must be performed one after another.
-   Ensures that resources are efficiently used by running only one Pod at a time.
   
> To apply this file use command :-
> **kubectl apply -f non-parallel-job.yaml**
> To check the job:-
> **kubectl get jobs**

## Parallel-job.yaml

A **parallel Job** in Kubernetes is a type of Job configuration that allows multiple Pods to run concurrently to complete a specified number of instances of the job successfully. This means Kubernetes will manage and execute several Pods simultaneously, each performing the same task independently until the desired number of successfully completed Pods is achieved.

**Usage Scenarios**:

-   **Parallel Processing**: Useful for tasks that can be divided into independent units of work that can run concurrently, thereby reducing overall processing time.
-   **Scalability**: Provides scalability by allowing Kubernetes to manage multiple instances of Pods based on the specified `parallelism` and `completions`.

> To apply this file use command :-
> **kubectl apply -f parallel-job.yaml**
> To check the job:-
> **kubectl get jobs**

## Scheduled-job.yaml

A **scheduled Job** in Kubernetes, typically referred to as a **CronJob**, allows you to automate the execution of Jobs at specific times or intervals, similar to how cron jobs work in Unix-like systems. This feature is beneficial for running recurring tasks, periodic batch jobs, or any task that needs to be executed on a regular schedule within a Kubernetes cluster.

**Usage Scenarios**:

-   **Regular Maintenance Tasks**: Automate routine maintenance tasks such as database backups, log cleanup, or system health checks.
-   **Scheduled Jobs**: Execute tasks that need to occur daily, weekly, monthly, or at custom intervals based on business requirements.
- **Scheduled Deployments**: Automate deployments of applications or updates during off-peak hours to minimize impact on users.

> To apply this file use command :-
> **kubectl apply -f scheduled-job.yaml**
> To check the job:-
> **kubectl get jobs**
