SJF vs Priority CPU Scheduling Simulator

A desktop Java application that simulates and compares two classic CPU scheduling algorithms — Shortest Job First (SJF) and Priority Scheduling (both non-preemptive) — with a graphical interface for input, visualization, and performance analysis.

Overview

This project was built as part of an Operating Systems course to demonstrate how different CPU scheduling algorithms affect process execution order and performance. Users can enter a set of processes (with arrival time, burst time, and priority), run both algorithms, and compare the results side by side.

Features


Two scheduling algorithms: Non-preemptive SJF and non-preemptive Priority scheduling.
Interactive GUI: Built with Java Swing (and Swift for additional GUI components) for entering process data and viewing results.
Gantt chart visualization: Graphically displays the execution timeline for each algorithm.
Performance metrics: Automatically calculates Waiting Time (WT), Turnaround Time (TAT), and Response Time (RT) for every process, plus averages for comparison.
Side-by-side comparison table: Lets you evaluate which algorithm performs better for a given workload.
Exportable results: Save simulation output to a log file.


Tech Stack


Language: Java (Swing for desktop GUI), Swift
Architecture: Simple layered design separating models (model), scheduling logic (scheduler), metrics (metrics), GUI (gui), and utilities (util)


Project Structure

src/main/java/
├── com/mycompany/os2/
│   └── OS2.java              # Application entry point
├── gui/
│   ├── MainGUI.java          # Main Swing window: inputs, tables, results
│   └── GanttChartPanel.java  # Custom panel that draws the Gantt chart
├── scheduler/
│   ├── SJFScheduler.java     # Non-preemptive SJF implementation
│   └── PriorityScheduler.java# Non-preemptive Priority implementation
├── metrics/
│   └── MetricsCalculator.java# Computes average WT, TAT, RT
├── model/
│   ├── Process.java          # Process data model (AT, BT, Priority, etc.)
│   └── GanttData.java        # Gantt chart segment model
└── util/
    └── FileSaver.java        # Saves results to a text log

How to Run


Make sure you have a JDK (Java 8 or later) installed.
Compile the source files:


bash   javac -d out $(find src/main/java -name "*.java")


Run the application:


bash   java -cp out com.mycompany.os2.OS2


Enter process details (ID, Arrival Time, Burst Time, Priority) in the input table, choose an algorithm, and view the generated Gantt chart and metrics.


How It Works


SJF: At each point in time, the scheduler picks the process with the shortest burst time among those that have arrived and are not yet completed.
Priority Scheduling: At each point in time, the scheduler picks the process with the highest priority (lowest priority number) among those that have arrived; ties are broken by earliest arrival time, then shortest burst time.
For both algorithms, the simulator tracks completion time and derives waiting time, turnaround time, and response time for every process.


Future Improvements


Add preemptive variants (SRTF, Preemptive Priority) for a fuller comparison.
Add starvation detection and aging.
Export results as PDF/CSV in addition to plain text logs.


Author

Yassin Mohamed — GitHub | LinkedIn
