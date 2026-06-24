# Phase 2 - Linux Authentication Log Investigation (SOC Analyst Lab)

## Overview

This phase focuses on investigating authentication activity from a SOC
Analyst perspective.

The objective is to simulate a security event where a Linux server
receives suspicious SSH login attempts and investigate the activity
using system logs.

Environment: - Kali Linux (Analyst Machine) - Metasploitable 2 (Target
Server)

Investigation flow:

Event -\> Log Evidence -\> Analysis -\> Finding -\> Recommendation

------------------------------------------------------------------------

## Lab Environment

Kali Linux: 192.168.189.130

Metasploitable 2: 192.168.189.129

------------------------------------------------------------------------

## Tools Used

  Tool               Purpose
  ------------------ --------------------------------
  Kali Linux         Security analysis environment
  Metasploitable 2   Vulnerable Linux target
  SSH                Generate authentication events
  auth.log           Authentication investigation

------------------------------------------------------------------------

## Objective

-   Generate failed SSH authentication attempts
-   Analyse Linux authentication logs
-   Identify suspicious login activity
-   Document findings like a SOC analyst

------------------------------------------------------------------------

## Investigation Process

### Generate Failed SSH Attempts

From Kali Linux:

ssh fakeuser@192.168.189.129

Incorrect credentials generate authentication failure events on the
target system.

------------------------------------------------------------------------

## Authentication Log Analysis

Linux stores authentication events in:

/var/log/auth.log

View failed login attempts:

cat /var/log/auth.log \| grep Failed

Example:

Failed password for invalid user fakeuser from 192.168.189.130

------------------------------------------------------------------------

# Security Findings

## Finding 1: Multiple Failed SSH Authentication Attempts

Severity: Medium

Description: Multiple unsuccessful SSH login attempts were detected.

Evidence: Log Source: /var/log/auth.log

Observed: Failed password for invalid user fakeuser from 192.168.189.130

Impact: Possible password guessing or brute-force behaviour.

Recommendation: - Use strong passwords - Enable SSH key authentication -
Restrict SSH access - Monitor authentication failures

------------------------------------------------------------------------

## Finding 2: Weak SSH Configuration

Severity: Medium

Description: The target system supports older SSH algorithms:

ssh-rsa ssh-dss

Risk: Deprecated cryptographic algorithms may weaken secure
communication.

Recommendation: - Upgrade SSH server - Disable deprecated algorithms -
Use modern cryptographic standards

------------------------------------------------------------------------

## SOC Skills Practiced

-   Linux log analysis
-   SSH investigation
-   Authentication event analysis
-   Security documentation
-   Incident reporting

------------------------------------------------------------------------

## Future Improvements

-   Integrate logs with a SIEM platform
-   Create authentication dashboards
-   Analyse Windows Event Logs
-   Correlate packet and log evidence

------------------------------------------------------------------------

## Disclaimer

This project was performed in an isolated cybersecurity lab environment
using intentionally vulnerable systems.
