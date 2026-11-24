# Project 5 – Secure Linux Server Permissions

## Overview
This project demonstrates user-based access control on an Ubuntu Linux server using Linux users, groups, directory ownership, and file permissions.

## Objectives
- Create separate Linux users and groups.
- Configure directory ownership and permissions.
- Provide read-only access to authorized users.
- Provide read and write access to authorized users.
- Prevent unauthorized access to protected directories.

## Users and Groups

| User | Group | Access |
|---|---|---|
| p5_reader | p5_readers | Read-only |
| p5_writer | p5_writers | Read and write |

## Directory Structure

```text
/srv/project5/
├── reader/
│   └── readme.txt
└── writer/
    ├── readme.txt
    ├── newfile.txt
    └── evidence-test.txt
```

## Permissions

| Resource | Permission | Purpose |
|---|---|---|
| /srv/project5 | 711 | Allows directory traversal |
| reader directory | 750 | Reader group access |
| writer directory | 770 | Writer group read/write |
| Reader file | 640 | Owner and group read access |
| Writer files | 660 | Owner and group read/write access |

## Testing and Validation

### Successful operations
- Reader successfully accessed the reader document.
- Writer successfully accessed the writer document.
- Writer successfully created and modified a file.

### Restricted operations
- Reader was denied write access to the writer directory.
- Writer was denied read access to the reader directory.
- Reader was denied write access to the reader directory.

All unauthorized operations returned `Permission denied`.

## Technologies Used
- Ubuntu Linux
- Bash
- Linux users and groups
- chmod
- chown
- sudo

## Evidence
The `evidence/` directory contains screenshots demonstrating user and group configuration, permissions, authorized access, and denied-access tests.

## Conclusion
Successfully implemented and tested Linux-based access control using users, groups, ownership, and file permissions. The project demonstrates the principle of least privilege by restricting users to their designated resources.
