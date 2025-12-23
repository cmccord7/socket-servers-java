<p align="center">
  <h1 align="center">Iterative vs Concurrent Socket Servers</h1>
  <h3 align="center">Java Client–Server Performance Analysis</h3>
</p>

<p align="center">
  CNT4504 – Computer Networks & Distributed Processing  
  <br />
  University Coursework Project
</p>

---

## Overview

This repository contains two Java-based client–server implementations developed to analyze how **server architecture impacts performance**, specifically **turn-around time** under increasing client load.

The projects compare a **single-threaded (iterative)** server with a **multi-threaded (concurrent)** server using identical workloads and testing methodology.

---

## Projects Included

### Iterative Socket Server (ISS)

A **single-threaded server** that processes **one client request at a time**, handling all incoming connections serially.
 
**Key Characteristics**
- One request processed at a time
- Requests queued automatically by `ServerSocket`
- Simple design with limited scalability

**Supported Operations**
- Date & Time  
- Uptime  
- Memory Usage  
- Netstat  
- Current Users  
- Running Processes  

**Full Technical Report**  
[Iterative Server Report (PDF)](docs/ISS_Report_McCord_Holmes.docx)

---

### Concurrent Socket Server (CSS)

A **multi-threaded server** that spawns a **new thread per client request**, allowing multiple clients to be processed in parallel.

**Key Characteristics**
- Parallel request handling
- Improved responsiveness under load
- Higher scalability with increased complexity

**Supported Operations**
- Date & Time  
- Uptime  
- Memory Usage  
- Netstat  
- Current Users  
- Running Processes  

**Full Technical Report**  
[Concurrent Server Report (PDF)](docs/CSS_Report_McCord_Holmes.docx)

---

## Client–Server Architecture

Both servers utilize a **multi-threaded client** capable of generating configurable numbers of concurrent requests.

**Client Features**
- User-defined server address and port
- Configurable request counts  
  - ISS: 1, 5, 10, 15, 20, 25 clients  
  - CSS: 1, 5, 10, 15, 20, 25, 100 clients  
- Metrics collected:
  - Individual request turn-around time  
  - Total turn-around time  
  - Average turn-around time  

Each request executes real Linux system commands on the server, and elapsed time is measured from transmission to response.

---

## Key Findings (Summary)

- Increasing client load **significantly increases turn-around time** in the iterative server
- The concurrent server maintains **lower average latency** as client count increases
- Iterative servers are suitable for:
  - Low-traffic environments
  - Simple or embedded systems
- Concurrent servers are better suited for:
  - Multi-user systems
  - Performance-sensitive applications
  - Scalable network services

Detailed charts and analysis are available in the full reports.

---

