# Building a SIEM Dashboard Using Splunk

## Abstract

This project demonstrates the implementation of a lightweight Security Information and Event Management (SIEM) solution using Splunk Enterprise on Windows 11. The dashboard collects and analyzes Windows Security, System, and Application logs to provide real-time monitoring, security visibility, and event analysis.

## Project Overview

The objective of this project is to build a lightweight SIEM dashboard using Splunk Enterprise while utilizing Windows 11 as the primary log source. The system collects Windows Event Logs and visualizes security-related events through dashboards and SPL searches.

## Objectives

- Collect Windows Event Logs
- Monitor Security Events
- Detect Failed Login Attempts
- Analyze Authentication Activities
- Monitor System Events
- Monitor Application Events
- Create Security Dashboards
- Perform Basic Security Analysis

## Tools Used

- Windows 11
- Splunk Enterprise
- Splunk Universal Forwarder
- GitHub

## Log Sources

The following Windows logs are used:

- Windows Security Logs
- Windows System Logs
- Windows Application Logs

## Dashboard Panels

1. Windows Security Events
2. Failed Login Attempts
3. Top Source IPs
4. Authentication Activity Over Time
5. Windows Error Events
6. System Events Over Time
7. Event Severity and Type
8. Total Security Events

## Sample SPL Queries

### Failed Authentication

```spl
index=windows EventCode=4625
| stats count by host
```

### Successful Authentication

```spl
index=windows EventCode=4624
| stats count by host
```

### Authentication Activity

```spl
index=windows (EventCode=4624 OR EventCode=4625)
| timechart span=5m count
```

### System Events

```spl
index=windows sourcetype=WinEventLog:System
| timechart span=5m count
```

### Total Events

```spl
index=windows
| stats count as total_events
```

## Architecture

Windows 11
↓
Windows Event Logs
↓
Splunk Universal Forwarder
↓
Splunk Enterprise
↓
SPL Queries
↓
SIEM Dashboard

## Expected Outcomes

- Centralized Log Collection
- Security Event Monitoring
- Failed Login Detection
- Authentication Monitoring
- Windows Event Analysis
- Dashboard Visualization

## Conclusion

This project demonstrates how Splunk Enterprise can be used as a lightweight SIEM solution on a Windows-based environment. It provides centralized logging, event monitoring, and dashboard-based visualization for security analysis.

## Author

Bikki Patel

## GitHub Repository

Building a SIEM Dashboard Using Splunk
