# Ticketing System Simulation

## Overview

This project simulates a ticketing system using C++11 threading. It demonstrates how threads can be managed and synchronized using an atomic variable to control access and ensure that each thread executes its task in a specific order. The system involves retrieving tickets, performing tasks, and logging the activities of each thread.

## Features

- **Multithreading**: Utilizes C++11 threads to perform concurrent tasks.
- **Atomic Operations**: Uses `std::atomic` to manage thread execution order.
- **File Logging**: Logs thread activities to an output file.
- **User Verification**: Performs a simple user verification before running the simulation.

## Code Explanation

### Key Components

1. **`executeTicketingSystemParticipation` Function**
   - Takes a ticket number and ensures that threads proceed in the correct order based on their ticket number.
   - Logs the start and completion of each thread's task.
   - Uses `std::this_thread::yield()` to yield control to other threads while waiting for the thread's turn.

2. **`runSimulation` Function**
   - Verifies the user by comparing the username from a `.user` file.
   - Initializes and launches multiple threads, each with a unique ticket number.
   - Joins all threads to ensure they complete before proceeding.
   - Calls `manageTicketingSystem()` to manage and finalize the ticketing system.

3. **`getUsernameFromUserFile` Function**
   - Retrieves the username from a `.user` file for user verification.

4. **`manageTicketingSystem` Function**
   - Manages the ticketing system by ensuring that all threads complete their tasks.
   - Logs the status of the threads and writes to an output file.

5. **`main` Function**
   - Parses command-line arguments to set the number of threads, username, and part ID.
   - Calls `runSimulation()` to start the simulation process.

### Dependencies

- C++11 standard or higher
- Standard C++ library

## Installation

1. **Clone the repository**:

    ```bash
    git clone https://github.com/Yogender21505/ticketing-system-simulation.git
    cd ticketing-system-simulation
    ```

2. **Compile the code**:

    ```bash
    g++ -std=c++11 -o ticketing_system_simulation main.cpp
    ```

3. **Run the simulation**:

    ```bash
    ./ticketing_system_simulation [numThreads] [username] [partId]
    ```

    Replace `[numThreads]` with the number of threads you want to simulate, `[username]` with your username, and `[partId]` with the part ID.

## Example Usage

```bash
./ticketing_system_simulation 5 yogender test
