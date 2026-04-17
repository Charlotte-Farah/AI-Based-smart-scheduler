# Smart CPU Scheduler

This project implements a **Smart CPU Scheduler** that leverages artificial intelligence to optimize process management in an operating system. By dynamically adjusting the time quantum and reordering the ready queue based on process behavior, the scheduler significantly reduces average waiting time and improves CPU utilization compared to traditional Round Robin algorithms.

## Project Overview
The core goal of this project is to build a scheduler that can distinguish between **CPU-bound** and **I/O-bound** processes using a machine learning classifier. 

* **Standard Round Robin:** Uses a fixed time quantum and treats all processes equally in a FIFO queue.
* **AI Smart Scheduler:** Uses a `DecisionTreeClassifier` to predict process types and applies dynamic logic:
    * **I/O-bound processes** are moved to the front of the queue to improve responsiveness.
    * **Dynamic Time Quanta** are assigned based on the prediction (e.g., 8 units for CPU-bound, 5 units for I/O-bound).

## Key Features
* **AI-Driven Classification:** Predicts process type based on features like "Time Needed" and "I/O Requests".
* **Dynamic Queue Reordering:** Prioritizes I/O-bound tasks to minimize CPU idle time.
* **Adaptive Time Quanta:** Tailors the execution burst to the nature of the process.
* **Performance Visualization:** Includes built-in simulations to compare Average Turnaround Time and Waiting Time between standard and smart schedulers using `matplotlib`.

## Performance Results
Based on the prototype simulation, the AI Smart Scheduler demonstrates a clear performance gain over the traditional baseline:
* **Standard Round Robin Avg Turnaround Time:** 20.33 mins
* **AI Smart Scheduler Avg Turnaround Time:** 16.33 mins

## Getting Started

### Prerequisites
To run the notebook, you need the following Python libraries:
* `matplotlib` (for generating performance charts)
* `scikit-learn` (for the `DecisionTreeClassifier`)

### Usage
1.  **Open in Google Colab:** Upload the `Copy_of_smart_cpu_schedular.ipynb` file to your Colab environment.
2.  **Execute the cells:**
    * **Phase 1:** Train the AI model with sample process data.
    * **Phase 2:** Run the baseline Standard Round Robin simulation.
    * **Phase 3:** Run the AI-based Smart Scheduler simulation.
    * **Phase 4:** Generate visual comparison reports and charts.

## Contributors
Developed as part of the **Operating System (CSC323)** course:
* Farah Amr Abdelghafour
* Logain Elsayed
* Mennat Allah Ayman
* Yehya Hany
* Mostafa Hany
