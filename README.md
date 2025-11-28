# Real-time-process-monitoring-dashboard
Project Title: Real Time Process Monitoring Dashboard

## Authors:

Shiwani Bhagat, Barnali Das, Satendra Yadav

## Overview

This project is a real-time system monitoring dashboard built using Dash and Plotly. It helps track system performance by visualizing key metrics like CPU usage, memory usage, disk space, and running processes. The dashboard updates automatically every 2 seconds to provide live insights.

## Features
1. **CPU Usage** : 
* Displays a real-time graph of CPU utilization over time.

* Helps in monitoring system performance and detecting high CPU usage.

2.**Memory Usage** : 
* Shows a pie chart representing used and available memory.

* Useful for tracking how much RAM is currently occupied.

3.**Disk Usage** : 
* Visualizes storage utilization in a simple, easy-to-understand format.

* Displays the percentage of disk space used vs. available.

4.**Running Processes Table** : 
* Lists the top 10 processes consuming the most CPU power.

* Shows details like Process ID (PID), Name, CPU %, and Memory %.

## Technologies Used
* **Dash** (for building the web-based dashboard)

* **Plotly** (for visualizing system data)

* **Psutil** (for fetching real-time system performance data)

* **Pandas** (for processing and structuring data)

 ## How to Run the Dashboard
1**Install dependencies:**

* pip install dash psutil pandas plotly
  
**Run the application:**

* python app.py

**Open in browser:**

* http://127.0.0.1:8060


## Module-Wise Breakdown
**1. Dashboard Layout (UI Module)**
* File: app.py
 * Libraries Used: dash, dash_table, html, dcc
* Functionality:

The main structure of the dashboard is built using Dash components.

The interface consists of graphs, tables, and auto-refresh intervals.

**Components included:**

* CPU Usage Graph (Line Chart)

* Memory Usage Pie Chart

* Disk Usage Pie Chart

Top Running Processes Table

**2. CPU Monitoring Module**
* Library Used: psutil, plotly.graph_objs
  **Functionality:**

Tracks CPU utilization in real time.

Maintains a history of CPU usage for the last 20 updates.

Displays data in a line graph for trend analysis.

**Key Function:**
'''python

    def update_cpu_graph(n):
        cpu_percent = psutil.cpu_percent(interval=None)
        return figure  # Updates the graph dynamically
    
**3. Memory Monitoring Module**
Library Used: psutil, plotly.graph_objs
**Functionality:**

* Fetches current memory usage from psutil.virtual_memory().

* Visualizes memory as a pie chart (Used vs Available).

* Helps monitor RAM consumption.

**Key Function:**

'''python

    def update_memory_graph(n):
         mem = psutil.virtual_memory()
         return figure  # Displays memory usage as a pie chart
    
**4. Disk Usage Monitoring Module**
Library Used: psutil, plotly.graph_objs
**Functionality:**

* Tracks the disk space usage in real time.

* Shows used vs free space in a pie chart.

**Key Function:**

'''python

    def update_disk_graph(n):
        disk = psutil.disk_usage('/')
        return figure  # Updates the disk usage pie chart
    
**5. Process Monitoring Module**
Library Used: psutil, pandas, dash_table
Functionality:

* Fetches all running processes and sorts them by CPU usage.

* Displays the top 10 CPU-consuming processes in a table.

**Information displayed:**

Process ID (PID)

* Process Name

* CPU Usage %

*mMemory Usage %

**Key Function:**

'''python

    def update_process_table(n):
        processes = []
        for proc in psutil.process_iter(attrs=['pid', 'name', 'cpu_percent', 'memory_percent']):
            processes.append(proc.info)
        return df.to_dict('records')  # Updates process table dynamically
        
## Snapshots Of The Dashboard

![newplot (4)](https://github.com/user-attachments/assets/25e7fc93-99eb-4d89-8d72-20fed69e17de)
![newplot (5)](https://github.com/user-attachments/assets/ad2c0ea7-c3ca-4e22-bf9a-349b1299b1ce)
![newplot (6)](https://github.com/user-attachments/assets/54bb96a6-9b91-4d29-a295-7e6eae237716)
![newplot (7)](https://github.com/user-attachments/assets/c7c313ce-69a8-4459-992d-0ebfe8904435)
![Screenshot (122)](https://github.com/user-attachments/assets/b76fbdb0-518a-4613-8b2d-be120f5b3ad6)




 ## License

This project is open-source and available under the MIT License.

## Contributions

Contributions are welcome! Feel free to fork this repository and submit a pull request.
