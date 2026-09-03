# Mini Company Linux Infrastructure

## Overview

A small multi-server company infrastructure designed and deployed
using Red Hat Enterprise Linux on AWS EC2.

The project simulates a real-world company environment with separate
web, application, and file server roles.

## Architecture

                         AWS VPC
                      172.31.0.0/16
                            │
              ┌─────────────┼─────────────┐
              │             │             │
              ▼             ▼             ▼
           web01          app01         file01
            RHEL           RHEL          RHEL
              │             │             │
           Apache       Application    File Server
              │
              └────── Private Network ────┘

       Users / Groups / Permissions / ACL
       AWS Security Groups + firewalld

## Technologies

- AWS EC2
- AWS VPC
- Red Hat Enterprise Linux
- Apache HTTP Server
- OpenSSH
- firewalld
- Linux users and groups
- Linux file permissions
- ACL
- Private IP networking

## Implementation

### 1. AWS Infrastructure

Created three RHEL EC2 instances inside an AWS VPC.

### 2. Server Configuration

Configured hostnames:

- web01
- app01
- file01

### 3. Private Networking

Configured `/etc/hosts` for internal hostname resolution.

### 4. User and Group Management

Created departmental groups:

- developers
- hr
- finance
- it

Created users and assigned them to appropriate groups.

### 5. Access Control

Configured Linux permissions and ACLs to provide
department-based access.

### 6. Web Server

Installed and configured Apache on web01.

### 7. Firewall

Configured RHEL firewalld and AWS Security Groups
to control network access.

## Testing

Documented connectivity, permissions, Apache availability,
and access-control tests.

## Screenshots

Screenshots demonstrating the infrastructure and configuration
are included in the screenshots directory.

## Future Improvements

- NFS centralized storage
- Persistent mounts
- Additional EBS storage
- Centralized log management
- Bash automation
- Automated backups

## What I Learned

- Linux server administration
- User and group management
- File permissions and ACL
- Apache configuration
- Linux firewall management
- AWS EC2 networking
- Troubleshooting Linux infrastructure
