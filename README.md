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
### 2. Access and Core Monitoring
The Netdata dashboard was accessed via a web browser at 
```
http://localhost:19999.
```
The dashboard automatically began monitoring the core system resources (CPU, memory, disk) and the Docker container environment.

Main Dashboard View: Captured the high-level overview of total disk reads/writes, CPU per node, and network traffic.

Node Information: Confirmed the live server status and system information, including the use of a Linux 6.6.87.2-microsoft-standard-WSL2 kernel within the Docker environment.

### 3. Deep Dive Exploration
CPU Metrics: Explored the Total CPU Utilization and Pressure Stall Information (PSI) for CPU.

Memory Metrics: Reviewed the Memory Pressure charts (Some Pressure and Full Pressure) and a gauge view of Total Available/Committed Memory.

Storage Metrics: Inspected the I/O Pressure Stall Information (PSI) for storage utilization.


Alerts Panel: Explored the Running Alerts tab, noting active warnings such as disk_inode_usage, disk_space_usage, and 10min_disk_utilization.

### 4. Log Exploration
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
*1. Main Dashboard Overview*
High-level system metrics overview.
<img width="2254" height="1341" alt="Screenshot 2025-10-03 092547" src="https://github.com/user-attachments/assets/ee11f53f-cf66-4920-b14e-c2ad5b90ba5a" />

*2. Nodes View and System Info*
Confirms the live status, Netdata version, and the underlying Docker/WSL2 environment.
<img width="2168" height="1066" alt="Screenshot 2025-10-03 092629" src="https://github.com/user-attachments/assets/1561d1d1-e08a-4007-a0fd-e46f70d0167c" />

*3. Detailed CPU Utilization and PSI*
Charts showing Total CPU Utilization and CPU Pressure Stall Information (PSI).
<img width="1802" height="1258" alt="Screenshot 2025-10-03 092732" src="https://github.com/user-attachments/assets/e8f60a15-eecb-4f41-b152-4214567dfe70" />

*4. Memory PSI* (Pressure Stall Information)
Detailed charts for Memory Pressure (Some Pressure and Full Pressure).
<img width="1770" height="1237" alt="Screenshot 2025-10-03 092747" src="https://github.com/user-attachments/assets/2a5afb06-2bf8-4911-aa26-dda3ab043c6b" />

*5. Memory Gauge View*
Metrics showing Total Available Memory and Total Committed Memory in GiB.
<img width="1661" height="444" alt="Screenshot 2025-10-03 092812" src="https://github.com/user-attachments/assets/cad9249f-7782-44fc-a541-ed51168d0c54" />

*6. Storage (Disk I/O) Pressure Stall Information*
Charts monitoring the disk I/O pressure on the system.
<img width="1683" height="960" alt="Screenshot 2025-10-03 092827" src="https://github.com/user-attachments/assets/e4df5e98-4534-42d9-ae5a-9e8abb40683c" />

*7. Alerts Dashboard*
The Alerts tab showing currently running warnings.
<img width="1798" height="1133" alt="Screenshot 2025-10-03 092940" src="https://github.com/user-attachments/assets/d21f3fbc-6660-47a5-90c1-6b29bc7dc1f3" />

*8. Terminal Log Exploration*
The output of ls -l /var/log/netdata inside the container, showing logs are directed to stdout/stderr.
<img width="1356" height="341" alt="Screenshot 2025-10-03 093258" src="https://github.com/user-attachments/assets/8491cc07-7af6-49e2-a174-83a7e978b885" />
