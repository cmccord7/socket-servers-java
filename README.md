Iterative vs Concurrent Socket Servers (Java) 
By Connor McCord and James Holmes

This repository contains two Java-based client–server implementations developed to analyze how server architecture impacts performance, specifically turn-around time under increasing client load.

The projects were completed as part of CNT4504 – Computer Networks & Distributed Processing and focus on comparing a single-threaded (iterative) server with a multi-threaded (concurrent) server using identical workloads and testing methodology.

Projects Included
Iterative Socket Server (ISS)

A single-threaded server that processes one client request at a time, handling all incoming connections serially.

Key characteristics:

One request processed at a time

Client requests are queued automatically by ServerSocket

Simple design but poor scalability under load

Supported operations:

Date & Time

Uptime

Memory Usage

Netstat

Current Users

Running Processes

Full technical report:
docs/Iterative_Server_Report.pdf

Concurrent Socket Server (CSS)

A multi-threaded server that spawns a new thread per client request, allowing multiple clients to be processed in parallel.

Key characteristics:

Parallel request handling

Improved responsiveness under load

Higher scalability at the cost of increased complexity

Supported operations:

Date & Time

Uptime

Memory Usage

Netstat

Current Users

Running Processes

Full technical report:
docs/Concurrent_Server_Report.pdf

Client–Server Architecture

Both servers are paired with a multi-threaded client capable of generating configurable numbers of concurrent requests.

Client features:

User-specified server address and port

Configurable request counts:

ISS: 1, 5, 10, 15, 20, 25 clients

CSS: 1, 5, 10, 15, 20, 25, 100 clients

Measures:

Individual request turn-around time

Total turn-around time

Average turn-around time

The client executes real Linux system commands on the server and measures the elapsed time for each request to complete.

Key Findings (Summary)

Increasing client load significantly increases turn-around time for the iterative server

The concurrent server maintains lower average latency as client count increases

Iterative servers are suitable for:

Low traffic environments

Simple or embedded systems

Concurrent servers are better suited for:

Multi-user systems

Performance-sensitive environments

Scalable network services

Detailed data, charts, and comparative analysis are available in the full reports.
