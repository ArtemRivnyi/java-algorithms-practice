# java-algorithms-practice: Algorithms and Data Structures Labs

![Java](https://img.shields.io/badge/Language-Java-007396?style=flat-square&logo=openjdk&logoColor=white )
![Apache Maven](https://img.shields.io/badge/Build%20Tool-Apache%20Maven-C71A36?style=flat-square&logo=apache-maven&logoColor=white )
![JUnit](https://img.shields.io/badge/Testing-JUnit-25A162?style=flat-square&logo=junit5&logoColor=white )

[![License](https://img.shields.io/badge/License-MIT-yellow.svg )](https://opensource.org/licenses/MIT )
[![Last Commit](https://img.shields.io/github/last-commit/ArtemRivnyi/java-algorithms-practice?label=Last%20Update&style=flat-square )](https://github.com/ArtemRivnyi/java-algorithms-practice/commits/master )

This repository is a collection of laboratory assignments focused on fundamental algorithms and data structures, implemented in Java. It serves as a practical demonstration of core computer science principles, with a strong emphasis on **performance analysis** and **efficient resource management**.

## 📝 Table of Contents

*   [🎯 Relevance for Technical Support / DevOps](#-relevance-for-technical-support--devops)
*   [✨ Features](#-features)
*   [🛠️ Technologies Used](#️-technologies-used)
*   [🚀 Quick Start](#-quick-start)
    *   [1️⃣ Clone the Repository](#1️⃣-clone-the-repository)
    *   [2️⃣ Build the Project](#2️⃣-build-the-project)
    *   [3️⃣ Run the Labs](#3️⃣-run-the-labs)
*   [🔬 Lab Details & Real-World Applications](#-lab-details--real-world-applications)
    *   [Lab 1: List Performance Comparison (ArrayList vs LinkedList)](#lab-1-list-performance-comparison-arraylist-vs-linkedlist)
    *   [Lab 2: Sorting Algorithms Performance Comparison](#lab-2-sorting-algorithms-performance-comparison)
    *   [Lab 3: Recursion and Iteration Examples](#lab-3-recursion-and-iteration-examples)
    *   [Lab 4: Binary Search Tree (BST) Implementation](#lab-4-binary-search-tree-bst-implementation)
    *   [Lab 5: Data Validation and Manipulation](#lab-5-data-validation-and-manipulation)
*   [🤝 Contributing](#-contributing)
*   [📄 License](#-license)
*   [🧰 Maintainer](#-maintainer)

---

## 🎯 Relevance for Technical Support / DevOps

While this project focuses on core programming concepts, the skills demonstrated are highly relevant and transferable to a **Technical Support** or **DevOps** role, particularly in environments dealing with high-performance or enterprise Java applications.

| Skill Demonstrated | Relevance to Technical Support / DevOps |
| :--- | :--- |
| **Performance Analysis (Labs 1 & 2)** | Ability to identify and troubleshoot performance bottlenecks in production systems. Understanding how data structure choice (`ArrayList` vs `LinkedList`) or algorithm selection (e.g., sorting) directly impacts system latency and resource consumption. |
| **Problem Decomposition & Logic (All Labs)** | Capacity to break down complex technical issues into smaller, manageable components. Essential for root cause analysis (RCA) and debugging in complex distributed systems. |
| **Resource Management (Lab 3: Recursion)** | Understanding the difference between iterative and recursive solutions, which is critical for managing stack memory and preventing stack overflow errors in application logs. |
| **Data Structure Fundamentals (Lab 4: BST)** | Knowledge of how data is stored and retrieved efficiently. This underpins database indexing, caching mechanisms, and log parsing efficiency. |
| **Data Validation & Regular Expressions (Lab 5)** | Practical skill in validating and manipulating data streams (e.g., log files, configuration files, user input). Regular expressions are a core tool for log analysis and monitoring. |
| **Standard Tooling (Maven, JUnit)** | Proficiency with industry-standard build and testing tools, ensuring the ability to set up, build, and test application components in a CI/CD pipeline or staging environment. |

---

## ✨ Features

*   **Fundamental Concepts**: Covers key algorithms and data structures such as lists, sorting, recursion, binary search trees, and data validation.
*   **Practical Implementation**: Provides ready-to-run examples for each lab, demonstrating concepts in practice.
*   **Java-Oriented Approach**: All assignments are implemented in Java, ensuring ease of understanding and code modification.
*   **Modular Structure**: Each lab is organized as a separate Maven module, simplifying navigation and study.
*   **Performance Comparison**: Includes analysis of the performance of different list implementations and sorting algorithms.
*   **Standard Tooling**: Utilizes standard Java development tools such as Maven for project building and JUnit for testing.

## 🛠️ Technologies Used

The project is built upon the following technologies and libraries:

*   **Java**: Primary programming language (JDK 19 or newer).
*   **Apache Maven**: Project management and build automation tool.
*   **JUnit**: Framework for unit testing.

## 🚀 Quick Start

To build and run these projects, follow these instructions:

### 1️⃣ Clone the Repository

```shell
git clone https://github.com/ArtemRivnyi/java-algorithms-practice.git
cd java-algorithms-practice
```

### 2️⃣ Build the Project

Navigate to each lab directory and build the project using Maven:

```shell
cd Lab01Task # or Lab02Sorting, Lab03Recursion, Lab04BST, Lab05
mvn clean install
```

### 3️⃣ Run the Labs

Run the main program for each lab:

**Run Lab01Task:**

```shell
mvn exec:java -Dexec.mainClass="ListPerformanceComparison"
```

**Run Lab02Sorting:**

```shell
mvn exec:java -Dexec.mainClass="SortingPerformance"
```

**Run Lab03Recursion:**

```shell
mvn exec:java -Dexec.mainClass="Main"
```

**Run Lab04BST:**

```shell
mvn exec:java -Dexec.mainClass="Node"
```

**Run Lab05:**

```shell
mvn exec:java -Dexec.mainClass="Main"
```

---

## 🔬 Lab Details & Real-World Applications

Each lab explores a specific concept, providing practical implementations, performance comparisons, and a link to a **real-world scenario** where the concept is applied.

### Lab 1: List Performance Comparison (`ArrayList` vs `LinkedList`)

**Concept:** Comparing the time complexity of sequential access, random access, and insertion operations between array-backed (`ArrayList`) and node-based (`LinkedList`) list implementations.

**Real-World Application:** **Optimizing Caching and Logging Systems.**
- **`ArrayList`** is preferred for read-heavy operations, such as accessing configuration parameters or cached data by index.
- **`LinkedList`** is more suitable for systems with frequent additions/removals at the ends, like implementing a high-throughput log queue or a simple Least Recently Used (LRU) cache where old entries are quickly removed from the head.

**Illustrative Performance Benchmarks (Time in milliseconds for 100,000 elements)**

| Operation | `ArrayList` (ms) | `LinkedList` (ms) | **Conclusion** |
| :--- | :--- | :--- | :--- |
| Sequential Access | 0.5 | 1.2 | `ArrayList` is faster due to contiguous memory. |
| Random Access (get(i)) | 0.001 | 15.0 | `ArrayList` is O(1), `LinkedList` is O(n). |
| Insert at End | 0.002 | 0.003 | Both are fast (amortized O(1)). |
| Insert at Start | 0.005 | 0.001 | `LinkedList` is O(1), `ArrayList` is O(n) due to shifting. |

***Note:** The values in this table are illustrative and represent expected performance characteristics. Actual runtimes depend on the execution environment.*

### Lab 2: Sorting Algorithms Performance Comparison

**Concept:** Implementing and comparing the time complexity and stability of various sorting algorithms (Bubble Sort, Merge Sort, Quick Sort, Shell Sort).

**Real-World Application:** **Efficient Log Processing and Report Generation.**
- **Quick Sort** (or its variants) is often used in standard library implementations for its excellent average-case performance, crucial for quickly sorting large datasets like server logs before analysis.
- **Merge Sort** is used when stability is required (e.g., sorting a list of transactions by time, then by amount, without disturbing the time order).

**Illustrative Performance Benchmarks (Time in milliseconds for 50,000 elements)**

| Algorithm | Time (ms) - Best Case (Sorted) | Time (ms) - Average Case (Random) | Time (ms) - Worst Case (Reversed) | **Complexity** |
| :--- | :--- | :--- | :--- | :--- |
| Bubble Sort | 150 | 12,000 | 15,000 | O(n²) |
| Shell Sort | 5 | 150 | 200 | O(n log² n) to O(n¹.⁵) |
| Merge Sort | 10 | 25 | 30 | O(n log n) |
| Quick Sort | 5 | 15 | 10,000 | O(n log n) (Avg), O(n²) (Worst) |

***Note:** The values in this table are illustrative and represent expected performance characteristics. Actual runtimes depend on the execution environment.*

### Lab 3: Recursion and Iteration Examples

**Concept:** Demonstrating the use of recursion and iteration for common problems (Factorial, Fibonacci) and comparing their execution overhead and memory usage.

**Real-World Application:** **Configuration Parsing and Tree Traversal.**
- **Recursion** is the natural choice for traversing hierarchical data structures like XML/JSON configuration files, file system directories, or network topology maps.
- **Iteration** is preferred for simple, linear tasks (like processing a list of users) to avoid the risk of **Stack Overflow Errors** that can occur with deep recursion in production environments.

### Lab 4: Binary Search Tree (BST) Implementation

**Concept:** Implementing a fundamental self-balancing data structure that allows for efficient insertion, deletion, and search operations (average O(log n)).

**Real-World Application:** **Database Indexing and Network Routing Tables.**
- The principles of a BST are the foundation for most **database indexing** mechanisms (like B-trees), which allow for near-instantaneous data retrieval.
- In networking, similar tree structures are used to build **routing tables** that quickly determine the optimal path for data packets.

### Lab 5: Data Validation and Manipulation

**Concept:** Practical application of regular expressions (regex) for data validation (e.g., phone numbers) and text manipulation (deletion, replacement).

**Real-World Application:** **Log File Analysis and Security Filtering.**
- **Technical Support** and **DevOps** teams heavily rely on regex for:
    1.  **Parsing Logs:** Extracting specific error codes, timestamps, or user IDs from unstructured log lines.
    2.  **Input Validation:** Ensuring configuration files or API payloads adhere to a strict format before processing.
    3.  **Security:** Masking sensitive data (like credit card numbers or PII) in logs before storage.

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork the repository, make improvements, and submit pull requests.

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🧰 Maintainer

**Artem Rivnyi** — Junior Technical Support / DevOps Enthusiast

* 📧 [artemrivnyi@outlook.com](mailto:artemrivnyi@outlook.com)  
* 🔗 [LinkedIn](https://www.linkedin.com/in/artem-rivnyi/)  
* 🌐 [Personal Projects](https://personal-page-devops.onrender.com/)  
* 💻 [GitHub](https://github.com/ArtemRivnyi)
