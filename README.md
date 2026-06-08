# Time Series Store

An in-memory time series data store with persistence, optimized for high-throughput insertions and efficient querying by time and tags. Designed to handle millions of data points with high-cardinality tags, while ensuring thread safety and durability.

---

## Project Overview

This project implements a time series database capable of:

- Inserting time-stamped data points with metric names, values, and arbitrary tags
- Querying data efficiently by time range and flexible tag filters
- Persisting data to disk to survive process restarts
- Supporting concurrent reads and writes safely
- Scaling to millions of data points with high-cardinality tag support

---

## Repository Structure

| File                     | Description                                      |
|--------------------------|------------------------------------------------|
| `TimeSeriesStore.java`   | Interface defining core store operations        |
| `DataPoint.java`         | Represents a single data point                   |
| `TimeSeriesStoreImpl.java` | In-memory store implementation with persistence |
| `TimeSeriesStoreTest.java` | Unit tests for the store implementation          |
| `generate_sample_data.py` | Python script to generate realistic sample data |

---

## Features & Requirements

- **Data Model:**  
  Each data point has a timestamp, metric name, numeric value, and a set of key-value tags.

- **Insertion:**  
  Fast, thread-safe insertion optimized for high-throughput workloads.

- **Querying:**  
  Retrieve data points by time ranges and tag filters without scanning the entire dataset.

- **Persistence:**  
  Data is persisted to disk and recovered automatically upon restart.

- **Concurrency:**  
  Fully thread-safe with minimal locking to maximize read/write parallelism.

- **Scalability:**  
  Designed to handle millions of data points and high-cardinality tag values efficiently.

---

## Getting Started

### Build & Test

Use Gradle to build and run tests:

```bash
# Build the project
./gradlew build

# Run unit tests
./gradlew test
