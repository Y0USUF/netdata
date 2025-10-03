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
