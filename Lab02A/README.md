# Lab02A - Windows VM CPU and Memory Analysis Report
**Student Name:** [Abdishakur Mohamed]
**Student ID:** [130541246]
**Course name:** [SPR100]
**Completion Date:** [24/09/2025]
**Lab Duration:** [5]
---
## Part 1: Virtual Machine Setup and Configuration
### 1.1 VM Configuration Summary
- **Hypervisor Name:** [VMware Workstation Pro]
- **Hypervisor Version:** [17.6.4 build-24832109]
- **CPU Cores:** [2]
- **Memory:** [4]
- **Storage:** [Hard disk capacity: 60 ]
- **Network:** [NAT]
### 1.2 VM Import and Startup Process
- **VM File Source:** [\\mydrive\courses\SPR100\Win10]
- **Import Method:** [pick amd drag]
- **VM Name:** [win10-amohamed242]
- **Storage Path:** [Path on your external SSD drive]
- **Startup Time:** [Time from power-on to login screen]
### 1.3 Initial System Configuration
- **Password Change Process:** [Settings > Accounts > Sign-in options**, then selected **Password** to create a new password ]
- **Git Installation:** [winget install Git.Git]
---
## Part 2: Windows System Analysis
### 2.1 CPU Analysis Results
#### System Information (msinfo32)
- **Processor Name:** [12th Gen Intel(R) Core(TM) i7-12700, 2112 MHz]
- **Number of Cores:** [2]
- **Logical Processors:** [2]
#### Task Manager CPU Analysis
- **Current CPU Utilization:** [5%  ]
- **Number of Virtual Processors:** [2]
- **CPU Base Speed:** [2.11 GHz]
- **CPU Current Speed:** [60s]
- **System Up Time:** [50 minute]
- **CPU Utilization Observations:** During a 60-second monitoring period, the CPU utilization remained low around 5%, indicating the VM was under light load. The system ran 145 processes during this time with stable CPU speed at base frequency. The VM detected 2 virtual processors, confirming CPU core allocation.]
### 2.2 Memory Analysis Results
#### System Information Memory Details
- **Total Physical Memory:** [4.00 GB]
- **Available Physical Memory:** [ 1.2 GB]
- **Total Virtual Memory:** [5.4 GB]
- **Available Virtual Memory:** [2.9 GB]
- **Virtual Memory Explanation:** [Total Virtual Memory is the combination of your physical RAM plus the paging file (disk space used as virtual RAM). Available Virtual Memory is the portion of this combined memory that is currently free and can be allocated for use. Essentially, virtual memory extends your system’s usable memory beyond the physical RAM by using disk space, helping the system run larger applications or multiple tasks simultaneously.]
#### PowerShell Memory Commands Output
**Physical Memory Information:**[Paste the output of: Get-WmiObject -Class Win32_PhysicalMemory]
- **Document:** ___PATH               : \\DESKTOP-4H9E4CT\root\cimv2:Win32_PhysicalMemory.Tag="Physical Memory 0" Capacity             : 4294967296
**Available Memory Information:**
[Paste the output of: Get-Counter "\Memory\Available MBytes"]
- **Available Memory:** [ \\desktop-4h9e4ct\memory\available mbytes :  1562]
### 2.3 System Performance Monitoring Results
#### Performance Monitor Data Collector Set
- **Data Collector Set Name:** Lab02A_Performance_Monitoring
- **Sample Interval:** 5 seconds
- **Duration:** [2:35]
- **Counters Monitored:**
- Processor: % Processor Time
- Memory: Available MBytes
- Physical Disk: % Disk Time
- **Log Location:** [C:\Users\Student\Documents or your chosen location]
#### Performance Data Summary
- **CPU Usage Range:** [ 2:35]
- **Memory Available Range:** [Minimum:1,285.00 Maximum:1,464.000]
- **Disk Usage Range:** [Minimum: 0.018 Maximum:7.411]
- **Performance Patterns Observed:** [CPU stayed almost flat (not really working much).
Memory available stayed stable, with only small changes.
Disk usage showed small spikes now and then but stayed low overall.]
#### Resource Monitor Observations
- **Peak CPU Usage:** [1%]
- **Peak Memory Usage:** [around (1464 MB used → so ~peak usage was memory dropping closer to 1285 MB available)]
- **Resource Usage During Activities:** [ When i did small tasks, the disk showed spikes. CPU and memory didn’t change much.]
#### Performance Monitor Data Collector Graph
![Performance Chart] (images/performance_chart.gif)
- **How You Extracted:** [drag and drop]
---
## Analysis and Conclusions
### Key Findings
1. **VM Configuration:** Setting up the VM was simple after importing the `.ova` file. I used VMware Workstation Pro, gave it 2 CPU cores, 4 GB of RAM, and 60 GB of storage. Everything worked smoothly on my external SSD.
2. **CPU Performance:** The VM's CPU stayed mostly idle, with low usage (around 5%). It had 2 virtual processors and ran at a base speed of 2.11 GHz, showing stable and efficient performance for basic tasks.
3. **Memory Management:** The system had 4 GB of physical memory, with around 1.2 GB free. Virtual memory helped extend RAM by using disk space. Memory usage was stable, and I better understand how Windows manages it.
4. **Performance Monitoring:** Using Task Manager, Resource Monitor, and Performance Monitor gave a good overview of CPU, memory, and disk usage. The tools were easy to use and helpful for tracking system behavior.
### Technical Insights
- **System Architecture Understanding:** I learned the difference between physical CPU cores and logical processors. I also got a better understanding of memory types like physical, virtual, cached, and pooled memory.
- **Virtualization Concepts:** I learned how VMs use the host's resources and how setting CPU, RAM, and disk affects performance. The VM can run smoothly if resources are balanced correctly.
- **Performance Monitoring Tools:** Windows tools like Task Manager, Performance Monitor, and Resource Monitor help watch system performance in real-time and over time. They're useful for diagnosing issues.
- **PowerShell Commands:** PowerShell can give quick system information. I used it to check memory status and physical RAM, and it’s useful for scripting and automation.
### Challenges and Solutions
- **VM Setup Challenges:** At first, Git didn’t work because the system didn’t recognize the path. I fixed it by adding Git manually to the system’s PATH environment variable.
- **Performance Monitoring Issues:** The data collector set setup was confusing at first, but after reviewing instructions and trying it again, it worked properly.
- **File Transfer Challenges:** Moving files from VM to host was tricky. I solved it by dragging and dropping files using VMware Tools, or saving them to a shared folder.
- **Solutions Applied:** I looked up fixes online, used system settings, and retried steps when something didn’t work. Problem-solving and patience helped.
- **Lessons Learned:** Next time, I’ll set up the environment more carefully (like checking PATH settings) and save work in shared folders right away to avoid transfer issues.
### Understanding Questions
- **Virtual Memory Concept:** Virtual memory is like backup RAM. When the real RAM is full, Windows uses part of the hard drive to keep things running smoothly.
- **VM Resource Allocation:** Giving a VM the right amount of CPU and RAM is important. Too little, and it runs slow. Too much, and the host system might lag.
- **Performance Monitoring Value:** Monitoring helps find out what’s using system resources, so admins can fix problems, improve speed, and plan upgrades if needed.
**Report Completion Time:** 5 hours  
**Confidence Level:** 9/10

---
**Report Completion Time:** [5]
**Confidence Level:** [Rate your understanding 7-10}
