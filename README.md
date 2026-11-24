# Network Parsing and Intrusion Detection Dashboard

## Project Overview

A Java-based network security monitoring and intrusion detection dashboard designed to analyze network logs, identify suspicious activity, and visualize network traffic patterns.

The system implements a multithreaded client-server architecture using TCP sockets, JavaFX, SQLite, and rule-based intrusion detection algorithms.

## Key Features

- Network traffic and CSV log parsing
- Live tcpdump output file monitoring
- Rule-based intrusion detection
- Suspicious login activity detection
- Port scanning detection
- Network traffic spike detection
- Multithreaded client-server architecture
- Concurrent network log analysis
- Interactive JavaFX security dashboard
- SQLite database integration
- Historical security event analysis
- Top source IP visualization

## Technologies Used

| Technology | Purpose |
|---|---|
| Java 25 | Application development |
| JavaFX 21 | Graphical user interface |
| TCP Sockets | Client-server communication |
| SQLite | Database storage |
| JDBC | Database connectivity |
| Maven | Build and dependency management |
| tcpdump | Network traffic collection |
| Regular Expressions | Network log parsing |
| ExecutorService | Multithreaded processing |
| WatchService | Live file monitoring |
| Git and GitHub | Version control |

## System Architecture

The application separates network log collection, parsing, intrusion analysis, database storage, and graphical visualization into independent modules.

The JavaFX client communicates with the analysis server through TCP sockets on port 5060.

The server uses a fixed thread pool of 10 workers to handle concurrent client requests.

The intrusion analyzer executes three detection tasks concurrently.

## Intrusion Detection Algorithms

| Detection Type | Detection Rule | Severity |
|---|---|---|
| Failed Login Activity | At least 5 events with status codes of 400 or above from the same source IP | High |
| Port Scanning | At least 10 distinct destination ports accessed by the same source IP | High |
| Traffic Spike | At least 20 network events within one minute | Medium |

These thresholds are experimental rules for identifying potentially suspicious activity.

The failed-login rule uses error status codes as a proxy for suspicious activity rather than directly validating authentication failures.

## Network Log Parsing

The system supports two types of network log input:

### CSV Log Parser

- Timestamp
- Source IP address
- Destination IP address
- Source port
- Destination port
- Network protocol
- Status code
- Data size

### Tcpdump Packet Parser

- TCP traffic parsing
- UDP traffic parsing
- ICMP traffic parsing
- IPv4 and IPv6 address parsing
- Source and destination port extraction
- Live monitoring of tcpdump output files

## Dashboard Features

### Security Dashboard

- Total network records
- Suspicious login IP addresses
- Potential port scanning IP addresses
- Traffic spike statistics
- Security alert messages
- Alert severity classification
- Top five source IP addresses

### Live Logs

- Real-time file change monitoring
- Automatic network log parsing
- Live network event visualization
- Automatic analysis of monitored traffic

### Analysis History

- Historical analysis results
- Stored security alerts
- Previous analysis retrieval
- Database history management

## Database Architecture

SQLite is used to store analysis results and network security events.

| Table | Purpose |
|---|---|
| analysis_jobs | Analysis metadata and statistics |
| log_events | Parsed network log records |
| alerts | Detected suspicious activities |

Database operations are implemented using JDBC.

## Repository Structure

| Directory | Description |
|---|---|
| analysis/ | Intrusion detection algorithms |
| parser/ | CSV and tcpdump log parsing |
| db/ | SQLite database management |
| model/ | Network log and alert data models |
| net/ | TCP client-server communication |
| server/ | Concurrent analysis server |
| ui/ | JavaFX graphical dashboard |
| pom.xml | Maven project configuration |

Java source files are located under:

    src/main/java/edu/project/intrusion/

## Installation and Execution

### Requirements

- JDK 25
- Apache Maven

### Build the Project

    mvn clean compile

### Start the Analysis Server

    mvn exec:exec

The server listens on TCP port 5060.

### Start the Dashboard

Open another terminal and run:

    mvn javafx:run

Select a CSV network log file or a tcpdump output file to begin analysis.

## Testing

The repository includes a ConcurrentClientSmokeTest class that generates synthetic network logs and sends concurrent analysis requests to the server.

The default test configuration uses five concurrent clients.

## Technical Skills Demonstrated

- Network Security
- Intrusion Detection Systems
- Network Traffic Analysis
- Security Log Analysis
- TCP/IP Networking
- Socket Programming
- Java Object-Oriented Programming
- Multithreading and Concurrency
- Client-Server Architecture
- Database Design and SQL
- JavaFX GUI Development
- Regular Expression Parsing
- Network Security Monitoring
- Maven Build Management

## Security and Privacy

Captured network traffic, runtime databases, and private log files are excluded from this public repository.

This project is an educational network security prototype. It is intended for authorized network monitoring and security analysis, rather than production deployment.

## Academic Project

NYU Tandon School of Engineering
