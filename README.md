## 🚀 Task: Monitor System Resources Using Netdata

### **Objective**
The primary goal was to install and run the **Netdata** monitoring agent via **Docker** to visualize system and application performance metrics in real-time.

### **Outcome**
This task helped to achieve a practical understanding of **lightweight monitoring** for servers and applications.

***

## **Implementation Details**

### 1. **Setup**
The Netdata Agent was launched as a Docker container using the provided command:

```bash
docker run -d --name netdata -p 19999:19999 netdata/netdata
```
2. Access and Core Monitoring
The Netdata dashboard was accessed via a web browser at 
```
http://localhost:19999.
```
The dashboard automatically began monitoring the core system resources (CPU, memory, disk) and the Docker container environment.

Main Dashboard View: Captured the high-level overview of total disk reads/writes, CPU per node, and network traffic.

Node Information: Confirmed the live server status and system information, including the use of a Linux 6.6.87.2-microsoft-standard-WSL2 kernel within the Docker environment.

3. Deep Dive Exploration
CPU Metrics: Explored the Total CPU Utilization and Pressure Stall Information (PSI) for CPU.

Memory Metrics: Reviewed the Memory Pressure charts (Some Pressure and Full Pressure) and a gauge view of Total Available/Committed Memory.

Storage Metrics: Inspected the I/O Pressure Stall Information (PSI) for storage utilization.


Alerts Panel: Explored the Running Alerts tab, noting active warnings such as disk_inode_usage, disk_space_usage, and 10min_disk_utilization.

4. Log Exploration
To address the requirement to explore logs in 
```bash
/var/log/netdata, a shell was executed inside the running 
```
netdata container:

```Bash

docker exec -it netdata bash
cd /var/log/netdata
ls -l
```
