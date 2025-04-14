# Day 2 – Hands-On with Linux Commands

## Overview

On Day 2 of the DevOps training, we dived deep into the world of **Linux commands**. As Linux is the backbone of most cloud and DevOps environments, mastering these commands is crucial for effectively managing systems and servers.

---

## Key Linux Concepts

We started by understanding how to navigate the Linux filesystem, manage files and directories, and perform essential administrative tasks. Here’s what we explored:

### Navigating and Managing Files

To begin with, we learned how to navigate around directories and manage files. Simple commands like `pwd` showed the current directory, and `ls` helped us list files and folders. We also covered commands for creating and deleting directories (`mkdir`, `rmdir`) and files (`touch`, `rm`). 

We also explored how to move and copy files using `mv` and `cp`.

### Viewing & Editing Files

Once we had our files in place, we learned to open and view them with commands like `cat`, `more`, and `less`. To edit files, we used text editors like `nano` and `vi`, which are essential for making quick changes directly from the terminal.

### Understanding Permissions & Ownership

Linux gives a lot of control over who can access and modify files. We explored commands to change file permissions using `chmod` and adjust ownership with `chown`. Knowing how to handle file permissions is vital for system security.

---

## System Monitoring & Management

A big part of DevOps is keeping track of the system’s performance. We went through several commands that let us monitor things like memory usage, disk space, and system uptime. Commands like `top` and `htop` showed real-time process info, while `df` and `free` let us check the health of the system resources.

### Working with Processes

Linux is all about multitasking, so understanding how to manage processes is key. We learned to list running processes with `ps` and how to stop or forcefully kill processes using `kill` or `kill -9`.

### Networking & Internet

DevOps often involves working with networking tools, and Day 2 didn’t disappoint. We got hands-on with commands like `ping` to check internet connectivity, and `curl` and `wget` for fetching web data. We also learned how to inspect network interfaces and active connections with `ifconfig` and `netstat`.

---

## Package and User Management

In addition to system monitoring and networking, we explored user management. We used `adduser` to create new users and `passwd` to manage passwords. On the package management side, we covered commands like `sudo apt update`, `sudo apt install`, and `sudo apt remove`, which help manage software packages on Linux-based systems.

---

## Conclusion

By the end of Day 2, I felt much more comfortable working in the Linux environment. I now have the skills to navigate filesystems, manage users, monitor system performance, and work with packages—all crucial tasks in a DevOps workflow.

Mastering these commands will definitely make it easier to interact with tools like Kubernetes, Docker, and other DevOps essentials as I continue my learning journey.

---

