# Basic Network Scanning with Nmap

## 1. Objective

The objective of this task is to perform a basic network security assessment
of a local machine using Nmap. The scan identifies open ports, running
services, service versions, and the operating system.

## 2. Tool Used

- Nmap 7.99.1
- Zenmap
- Windows 11

## 3. Target

Target IP:
127.0.0.1 (localhost)

The scan was performed only against the local machine.

## 4. Scans Performed

### Basic Scan

Command:

nmap 127.0.0.1

Purpose:

To identify open TCP ports and the services associated with them.

### Service and Version Detection

Command:

nmap -sV 127.0.0.1

Purpose:

To identify the services running on open ports and detect their versions
where possible.

### Operating System Detection

Command:

nmap -O 127.0.0.1

Purpose:

To identify the operating system of the target machine.

## 5. Operating System Result

Nmap identified the target operating system as:

Microsoft Windows 11

OS Details:

Microsoft Windows 11 24H2 - 25H2

## 6. Open Ports Identified

| Port | Service | Detected Information |
|------|---------|----------------------|
| 135/tcp | msrpc | Microsoft Windows RPC |
| 445/tcp | microsoft-ds | Microsoft-DS |
| 1521/tcp | oracle-tns | Oracle TNS Listener 11.2.0.2.0 |
| 3306/tcp | mysql | MySQL 8.0.41 |
| 7070/tcp | realserver? | Service identification uncertain |
| 8080/tcp | http | Oracle XML DB Enterprise Edition httpd |
| 16992/tcp | amt-soap-http? | Service identification uncertain |

## 7. Security Analysis

Open ports increase the attack surface of a system. Each open service
should be reviewed to determine whether it is required.

### Port 135 - Microsoft RPC

Microsoft RPC services are used by Windows for communication between
applications and services.

Security consideration:
Unnecessary exposure of RPC services can increase the attack surface.
Access should be restricted to trusted environments where appropriate.

### Port 445 - Microsoft-DS

This port is commonly associated with Windows file and network sharing.

Security consideration:
Unnecessary exposure of file-sharing services can increase security risk.
Access should be restricted to trusted networks.

### Port 1521 - Oracle TNS

This port is associated with the Oracle TNS listener.

Security consideration:
Database listener ports should not be unnecessarily exposed. Access
should be restricted and properly secured.

### Port 3306 - MySQL

This port is commonly used by MySQL database servers.

Security consideration:
Database services should be accessible only to required applications
or trusted hosts.

### Port 7070 - Realserver?

Nmap identified this service with uncertainty, indicated by the question mark.

Security consideration:
The actual application using this port should be identified. If the
service is unnecessary, it should be disabled.

### Port 8080 - HTTP

Nmap identified an HTTP service associated with Oracle XML DB Enterprise
Edition.

Security consideration:
The service should be reviewed for secure configuration, authentication,
and access control.

### Port 16992 - AMT SOAP HTTP?

Nmap identified this service with uncertainty.

Security consideration:
The actual service should be verified. Unnecessary services should be
disabled and access should be restricted.

## 8. Summary

The scan identified seven open TCP ports on the local Windows 11 machine.
The detected services included Microsoft RPC, Microsoft-DS, Oracle TNS,
MySQL, HTTP, and services whose identification was uncertain.

The results demonstrate that network services increase the attack surface
of a system. Services that are not required should be disabled, while
required services should be properly secured and access-controlled.

## 9. Ethical Use

This assessment was performed only against the local machine
(127.0.0.1). No external systems or unauthorized targets were scanned.

The purpose of this activity is educational and defensive security
assessment.

## 10. Evidence

The following screenshots are included as evidence:

- 01_basic_nmap_scan.png
- 02_nmap_service_version.png
- 03_nmap_os_detection.png

The complete scan results are documented in:

nmap_scan_results.txt